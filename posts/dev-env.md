# Developer Environment Guide

This is my personal guide to getting a working developer environment from scratch on macOS.

## Getting Started

First off, open System Preferences and choose the dark appearance. This is **very** important!!

After we have prevented eye strain, we need the Xcode Command Line Tools. Although they come preinstalled with Xcode, you can also get them seperately to avoid a large download.

After this, we can install [Homebrew](https://brew.sh/), a macOS package manager. Run this script:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

With Homebrew, we can now install packages without doing all the dirty work.

## Quick Look

These are not required to be installed as they just enhance the experience. These plugins extend Quick Look, one of my personal favorite features on macOS.

Install all the extensions with this one-liner:

```bash
brew cask install qlcolorcode qlstephen qlmarkdown quicklook-json qlprettypatch quicklook-csv betterzipql webpquicklook suspicious-package
```

## Internet

I only need one browser to access the internet, Google Chrome, although I also use others in order to ensure my web content works on different platforms. Homebrew includes a handy cask feature, which will let us install all of them in one go.

```bash
brew cask install google-chrome firefox
```

Safari is not included for obvious reasons (it is preinstalled).

We can go ahead and sign into Reddit and other websites using passwords from 1Password.

## Chatting

I use Discord and Slack to communicate. Luckily, Homebrew lets us install these too:

```bash
brew cask install discord slack
```

## Node.js

Of course, I need to ensure my projects work on the latest, stable, and LTS releases of Node.js, so I use a fast version switcher called [`n`](https://github.com/tj/n) instead. Thanks to Homebrew, we just need to run a simple command:

```bash
brew install n
```

This will start the installation of `n`. Once it is finished, install the versions we need:

```bash
n latest
n stable
n lts
```

Now we can install our ESLint utilities, like [my config](https://github.com/haykam821/ESLint-Config-Haykam) and [ESLint itself](https://eslint.org/):

```bash
npm install -g eslint eslint-config-haykam
```

We can also install [`nodemon`](https://github.com/remy/nodemon), a CLI tool allowing for automatic restart of scripts when a file changes:

```bash
npm install -g nodemon
```

Here is a one-liner to install all the packages listed above from NPM:

```bash
npm install -g eslint eslint-config-haykam nodemon
```

## Visual Studio Code

Go ahead and install Visual Studio Code from Homebrew:

```bash
brew cask install visual-studio-code
```

My theme is [Atom One Dark](https://marketplace.visualstudio.com/items?itemName=akamud.vscode-theme-onedark) and I use [file-icons](https://marketplace.visualstudio.com/items?itemName=file-icons.file-icons) to help me tell apart my files without having to look at the extension.

Here are my main user settings:

```json
{
    "workbench.colorTheme": "Atom One Dark",
    "workbench.iconTheme": "file-icons",
}
```

## Git

We should already have Git installed from Xcode Command Line Tools.

I prefer [GitHub Desktop](https://desktop.github.com/) as an interface for Git, and it can be installed directly from Homebrew:

```bash
brew cask install github
```

Start up GitHub Desktop and configure:

- Log into GitHub.
- Set the appearance to dark.
- Change the external editor to Visual Studio Code, which we installed earlier.

I usually clone the frequently used repos of mine to my disk as well.

## Databases

Now we can install [MariaDB](https://mariadb.com/) through Homebrew:

```bash
brew install mariadb
brew services start mariadb
```

This will install MariaDB, then allow Homebrew to auto-start it.

I use [Sequel Pro](https://sequelpro.com/), which is free despite its name, to interactively view and edit databases:

```bash
brew cask install sequel-pro
```

## Conclusion
