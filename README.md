#Installing Jekyll on Windows 7

##References
[Guide to Using Jekyll with Pages](https://help.github.com/articles/using-jekyll-with-pages)

[Running Jekyll on Windows](http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html)

[Jekyll on Windows](http://jekyllrb.com/docs/windows/#installation)

[StackOverflow Post](http://stackoverflow.com/questions/17280884/cant-install-nokogiri-for-ruby-in-windows)

##Installing Jekyll
1. Ruby - Jekyll requires the Ruby language. If you have a Mac, you've most likely already got Ruby. If you open up the Terminal application, and run the command ruby --version you can confirm this. Your Ruby version should begin with 1.9.3 or 2.0.0. If you've got that, you're all set. Skip to step #2. Otherwise, follow these instructions to install Ruby.

2. Ruby Development Kit

3. Nokogiri

Tried installing it, but turns out that Nokogiri is not yet working with x64 bit version of Ruby.

4. Bundler - Bundler is a package manager that makes versioning Ruby software like Jekyll a heck of a lot easier if you're going to be building GitHub Pages sites locally. If you don't already have Bundler installed, you can install it by running the command gem install bundler.

For me Bundler initially failed with cannot install RedPath...Needed the Ruby Development Kit (Yea I knew that) :P

Then Bundler completed but noted that Nokogiri failed to install.

5. Jekyll - The main event. You'll want to create a file in your site's repository called Gemfile and add the line gem 'github-pages'. After that, simply run the command, bundle install and you're good to go. If you decided to skip step #2, you can still install Jekyll with the command gem install github-pages, but you may run into trouble down the line. Here’s an example of a Gemfile you can use (placed in the root directory of your repository):

#*Note this is still a work in progress.
