Ohana API Documentation
=======================

A static website for the Ohana API documentation, built with [Slate](https://github.com/lord/slate).


Getting Started
---------------

### Install Prerequisites

You'll need to have the following software packages installed on your computer:

- Git
- Ruby 2.7.6
- A Ruby version manager, such as RVM, rbenv, chruby, or asdf
- Bundler — If Ruby is already installed, but the `bundle` command doesn't work,
run `gem install bundler` in a terminal.

If you already have all of the prerequisites installed, you can skip to the
next section. Otherwise, follow this [guide for installing Ruby on a Mac](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/),  or buy the [Ruby on Mac] script that can set everything up for you in minutes.

[Ruby on Mac]: https://www.rubyonmac.dev/pricing

### Install the code

#### Fork and clone

[Fork this repository to your GitHub account][fork].

Clone it on your computer and navigate to the project's directory:

    git clone https://github.com/<your GitHub username>/ohana-api-docs.git && cd ohana-api-docs

[fork]: http://help.github.com/fork-a-repo/

#### Install the dependencies:

    bundle install

### Run the website

    bundle exec middleman server

You can now see the docs at <http://localhost:4567>. The first three sections
are in `source/index.md`, and the rest of the documentation is in various
files in `source/includes`. As you make changes to any of the markdown files,
the browser should automatically update.

### Publish the website (for those who have write access to this repo)

    # after committing all changes
    git push origin master

    # after verifying that the code has been pushed to GitHub
    ./deploy.sh

Learn more about [editing Slate markdown](https://github.com/lord/slate/wiki/Markdown-Syntax).

### Note on JavaScript Runtime
For those who don't have JavaScript runtime or are experiencing JavaScript
runtime issues with ExecJS, it is recommended to add the `rubyracer` gem to
your gemfile and run `bundle` again.
