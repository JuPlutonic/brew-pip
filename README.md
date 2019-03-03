     _                                  _       
    | |__  _ __ _____      __     _ __ (_)_ __  
    | '_ \| '__/ _ \ \ /\ / /____| '_ \| | '_ \      brew pip installs python packages
    | |_) | | |  __/\ V  V /_____| |_) | | |_) |            inside of Homebrew.
    |_.__/|_|  \___| \_/\_/      | .__/|_| .__/ 
                                 |_|     |_|    

Install
-------

    $ brew install brew-pip

Usage
-----

    brew pip install mercurial        # install the latest mercurial package
    brew pip install django==1.2      # install django-1.2
    brew pip install ~/tox-1.3.tar.gz # can install local packages, too
    brew pip install -u django==1.3.1 # upgrade to django-1.3.1
    brew pip install -k ipython       # install ipython, but don't link it (i.e., keg-only)
    brew pip uninstall django         # uninstall a previously installed package
    brew pip reinstall django         # reinstall a package
    brew pip list                     # list installed packages
    brew pip -h                       # for help

Setup
-----

So python can load your installed libraries, you need to update your `PYTHONPATH`:

    export PYTHONPATH=$(brew --prefix)/lib/python2.7/site-packages

And for any scripts to be found, you need to update your `PATH`:

    export PATH=$PATH:$(brew --prefix)/bin

But doesn't everybody use virtualenv now?
-----------------------------------------

Why, yes, they do.  But that doesn't mean global installations are
totally useless.  What if you want to use a package *without* being
active in a virtualenv -- like say ipython?

With `brew pip` you can globally install a select few packages while
relying on virtualenv for everything else.

It's the best of both worlds.

Changelog
---------

v0.5.0 *(2019-03-03)*

- Install scripts to `bin` and not `share/python`
- Add fallback when HOMEBREW_CELLAR is not specified
- Match cli experience given by brew-cask

v0.4.1 *(2013-12-03)*

- Add a `--version` argument
- Handles `@rev` syntax correctly

v0.4.0 *(2011-12-28)*

- Much more robust handling of different package syntaxes
- Can install VCS packages
- Add test suite

v0.3.0 *(2011-12-26)*

- Add `brew-pip.rb` for Homebrew installation
- Can accept local source distributions for installation

v0.2.0 *(2011-12-25)*

- Use pip directly, instead of creating temporary formula files.
