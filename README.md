#Installing Jekyll on Windows 7

##References
* [Guide to Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages) from [GitHub](http://github.com)
* [Running Jekyll on Windows](http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html) from [Madhur Ahuja](http://www.madhur.co.in)
* [Jekyll on Windows](http://jekyllrb.com/docs/windows/#installation) from [Jekyll](http://jekyllrb.com)
* [Post](http://stackoverflow.com/questions/17280884/cant-install-nokogiri-for-ruby-in-windows) from [stackoverflow](http://stackoverflow.com)

##Getting Jekyll Installed

###Install Ruby
[Ruby](https://www.ruby-lang.org/) - Jekyll requires the Ruby language. If you have a Mac, you most likely already have Ruby installed. If you open up the Terminal application, and run the command ```ruby --version``` you can confirm this. Your Ruby version should begin with ```1.9.3``` or ```2.0.0```. If you've got that, you're all set. Otherwise,

1. Install Ruby from [Rubyinstaller.org](http://rubyinstaller.org/downloads/). You can just double-click the downloaded file to install Ruby for Windows.  I installed mine into **C:\Ruby193**.

*I would suggest installing Ruby v1.9.3 as Nokogiri has issues with x64 Ruby and Ruby 2.0.0 has issues on windows in general.*

###Install the Ruby Development Kit
[Ruby Development Kit](http://rubyinstaller.org/downloads/) - Download the “DEVELOPMENT KIT” installer that matches the Windows architecture and the Ruby version just installed.

1. Install the Ruby development kit from the [same location](http://rubyinstaller.org/downloads/) above and extract it to a folder such as **C:\RubyDevKit**.

2. Next fire up your favorite Command Line Interface (CLI) (I prefer [PowerShell](http://en.wikipedia.org/wiki/Windows_PowerShell)) and navigate to the **C:\RubyDevKit** folder.  Run ```ruby dk.rb init``` to have Ruby create the initial **config.yaml** file.

3. Open the **config.yaml** file to ensure it looks like similar to mine.

4. In the same **C:\RubyDevKit** folder run ```ruby dk.rb install``` to install the Ruby Development Kit.

```YAML
# This configuration file contains the absolute path locations of all
# installed Rubies to be enhanced to work with the DevKit. This config
# file is generated by the 'ruby dk.rb init' step and may be modified
# before running the 'ruby dk.rb install' step. To include any installed
# Rubies that were not automagically discovered, simply add a line below
# the triple hyphens with the absolute path to the Ruby root directory.
#
# Example:
#
# ---
# - C:/ruby19trunk
# - C:/ruby192dev
#
---
- C:/Ruby193
```

### Install Bundler
[Bundler](http://bundler.io/) - Bundler is a package manager that makes versioning Ruby software like Jekyll a heck of a lot easier if you're going to be building GitHub Pages sites locally.

1. Install it by running the command ```gem install bundler``` from the same CLI in the **C:\RubyDevKit** folder.

###Install Jekyll

[Jekyll](http://jekyllrb.com/) - Transform your plain text into static websites and blogs.

1. Create a file in your site's repository called ```Gemfile``` and add the line ```gem 'github-pages'```. Most windows editors give you grief about creating files without extensions.  Feel free to download [mine](https://github.com/iamgabeortiz/iamgabeortiz.github.io/blob/master/Gemfile) and use it.

2. After that, simply run the command, ```bundle install``` from within your sites local repository folder and you're good to go.

3. Here’s an example of a Gemfile you can use (placed in the root directory of your repository):
```ruby
source 'https://rubygems.org'
gem 'github-pages'
require 'rbconfig'
gem 'wdm', '~> 0.1.0' if RbConfig::CONFIG['target_os'] =~ /mswin|mingw/i
```

*You will find that you may have to run ```bundle install``` again after adding the Auto-Configuration portion to the ```Gemfile``` or if using my [my](https://github.com/iamgabeortiz/iamgabeortiz.github.io/blob/master/Gemfile) ```Gemfile``` as Bundle will require the wdm gem.*

###Running jekyll
To run Jekyll in a way that matches the GitHub Pages build server, run Jekyll with Bundler. Use the command ```bundle exec jekyll serve``` in the root of your repository, and your site should be available at ```http://localhost:4000```. For a full list of Jekyll commands, see [the Jekyll documentation](http://jekyllrb.com/docs/usage/).

###Keeping Jekyll up to date
Jekyll's an [active open source project](https://github.com/mojombo/jekyll), and is updated frequently. As the GitHub Pages server is updated, the software on your computer may become out of date, resulting in your site appearing different locally from how it looks when published on GitHub. To keep Jekyll up to date, you can run the command ```bundle update```.

###Conclusion
The Jekyll install was an interesting experience and you can find more information and troubleshooting steps on the sites whose information I referenced.
