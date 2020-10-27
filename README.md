# EMac
EMac is to describe for my daily-used softwares, as well as configurations and preference on MacOS, inspired by the idea: [infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_Code)

## Update OS related package
1. Update operate system to the latest version
2. brew update
3. xcode-select --install
4. sudo xcodebuild -license accept

## Terminal
[ITerm](https://www.iterm2.com/)

## Shell
[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

configurations in `~/.zshrc`
```shell
ZSH_THEME="arrow"
export EDITOR='vim'
plugins=(git ruby rails autojump docker encode64 bundler zsh-autosuggestions)
```

## IDE
the built-in `vi` with OS is not the `vim` developer used to use, it only has limited functions, so `vim` must be installed mannually.
```shell
$ brew install vim --with-override-system-vi
```
### vim configuration
follow the instruction: [https://github.com/Dogzhou/vim_config](https://github.com/Dogzhou/vim_config)

### install ctags
normally the result of executing `ctags -R` will cause an issue
```shell
$ ctags -R --exclude=.git --exclude=log *
ctags: illegal option -- R
usage: ctags [-BFadtuwvx] [-f tagsfile] file ...
```

That's saying new `ctags` should be installed rather than original one.
```shell
$ brew install ctags
```
alias ctags in `~/.zshrc`
```shell
alias ctags="`brew --prefix`/bin/ctags"
```

## GIT
install
```shell
$ brew install git
```
configuration
```shell
$ git config --global user.username yourusername
$ git config --global user.email youremail
$ git config --global pull.rebase true
$ git config --global core.autocrlf input
```
### global ignore
I've seen lots of projects' git ignore file contain OS related or IDE related files, such as `.DS_Store`, `.idea`, or logs file, however project specified ignore file should not care about it, as different developers work with different OS/IDE, git ignore file will become a monolith if every one put their personal OS/IDE ignore pattern there.
I highly recommend every developer maintains their own global git ignore file according to their preference, so `.gitignore` file inside project repository only care about project own files at framework/language level.

```shell
$ git config --global core.excludesfile ~/.gitignore_global
```

Edit `~/.gitignore_global`

## Development Environment Setup

### rbenv
Use [rbenv](https://github.com/rbenv/rbenv) to manage local ruby versions.

```shell
$ brew install rbenv
$ rbenv init
$ gem install bundler
```

### node
```shell
$ brew install node
```

### Elixir
```shell
$ brew install elixir
```

## Command Line Tool

### [autojump](https://github.com/wting/autojump)
autojump provides a faster way to navigate your filesystem

### [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)

### mycli & pgcli
[MyCLI](https://www.mycli.net/) is a command line interface for MySQL, MariaDB, and Percona with auto-completion and syntax highlighting.
[Pgcli](https://www.pgcli.com/) Pgcli is a command line interface for Postgres with auto-completion and syntax highlighting.

### magic-wormhole
[magic-wormhole](https://github.com/warner/magic-wormhole) helps get things from one computer to another, safely.

### [docker](https://www.docker.com/)

## Softwares
### xcode
install xcode from [app store](https://developer.apple.com/xcode/)

### [1passowrd](https://1password.com/)

### VSCODE
I personally use [VSCODE](https://code.visualstudio.com/) to do front-end work, it's both lightweight and versatile, configurations and plugins can be uploaded to cloud, which means it's easy to reproduce an identical IDE on a new system. Infrastructure as Code!!

My personal setting locates [here](https://gist.github.com/Dogzhou/70091ca501d339f4cb2c9ea1bcdb585b)

### browsers
No need to say much about [Chrome](https://www.google.com/chrome/) and [firefoxj](https://www.mozilla.org/en-US/firefox/new/), extensions would be sync automatically as soon as login account.

### [Slack](https://slack.com/)

### [Skype](https://skype.com/)

### [Evernote](https://evernote.com/)

### [Dropbox](https://www.dropbox.com)

### [Spectacle](https://www.spectacleapp.com/)
Move and resize windows with ease. Window control with simple and customizable keyboard shortcuts.

### [Sketch](https://www.sketchapp.com/)

### [Balsamiq Mockup 3](https://balsamiq.com/download/)
It's been so fast and easy to do mockup stuff with `Balsamiq Mockup 3`, it provides a cute means with comprehensive widgets, Mockup a web page or mobile can be within minutes.

### [Flux](https://justgetflux.com/)
It makes the color of your computer's display adapt to the time of day, warm at night and like sunlight during the day. it does works though I never realize it.

### [IINA](https://lhc70000.github.io/iina/)
The best video player for macOS ever!!
