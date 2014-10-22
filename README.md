Ohana API Documentation
=======================

A static website for the Ohana API documentation, built with [Slate](https://github.com/tripit/slate).


Getting Started
---------------

### Install Prerequisites

You'll need to have the following software packages installed on your computer:

- Git
- Ruby 2.1+
- RVM

If you already have all of the prerequisites installed, you can skip to the
next section. Otherwise, install the [Build tools][build-tools] and
[Ruby with RVM][ruby].

[build-tools]: https://github.com/codeforamerica/howto/blob/master/Build-Tools.md
[ruby]: https://github.com/codeforamerica/howto/blob/master/Ruby.md

### Install the code

#### Fork and clone

[Fork this repository to your GitHub account][fork].

Clone it on your computer and navigate to the project's directory:

    git clone https://github.com/<your GitHub username>/ohana-api-docs.git && cd ohana-api-docs

[fork]: http://help.github.com/fork-a-repo/

#### Install the dependencies:

    bundle install

### Run the website

    middleman server

You can now see the docs at <http://localhost:4567>. The first three sections
are in `source/index.md`, and the rest of the documentation is in various
files in `source/includes`. As you make changes to any of the markdown files,
the browser should automatically update.

### Publish the website (for those who have write access to this repo)

    # after committing all changes
    git push origin master

    # after verifying that the code has been pushed to GitHub
    rake publish

Learn more about [editing Slate markdown](https://github.com/tripit/slate/wiki/Markdown-Syntax).
