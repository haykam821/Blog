# Developer Environment Guide

This is my personal guide to getting a working developer environment from scratch on macOS.

## Getting Started

To get started, we need the Xcode Developer Tools. Although they come preinstalled with Xcode, you can also get them seperately to avoid a large download.

After this, we can install [Homebrew](https://brew.sh/), a macOS package manager. Run this script:

    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

With Homebrew, we can now install packages without messing up anything ourselves.

## Node.js

Of course, I need to ensure my projects work on the latest, stable, and LTS releases of Node.js, so I use a fast version switcher called [`n`](https://github.com/tj/n) instead. Thanks to Homebrew, we just need to run a simple command:

    brew install n

This will start the installation of `n`. Once it is finished, install the versions we need:

    n latest
    n stable
    n lts

Now we can install our ESLint utilities, like [my config](https://github.com/haykam821/ESLint-Config-Haykam) and [ESLint itself](https://eslint.org/):

    npm install -g eslint eslint-config-haykam

We can also install [`nodemon`](https://github.com/remy/nodemon), a CLI tool allowing for automatic restart of scripts when a file changes:

    npm install -g nodemon

Here is a one-liner to install all the packages listed above from NPM:

    npm install -g eslint eslint-config-haykam nodemon

## Conclusion
