# EMac
EMac is to describe for my daily-used softwares, as well as configurations and preference on MacOS, inspired by the idea: [infrastructure as code](https://en.wikipedia.org/wiki/Infrastructure_as_Code)

## Homebrew
```
https://brew.sh/
```

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
```
ZSH_THEME="arrow"
export EDITOR='vim'
plugins=(git autojump encode64 zsh-autosuggestions zsh-bat)

git config --global pull.rebase true
git config --global fetch.prune true
git config --global diff.colorMoved zebra
```

## IDE
the built-in `vi` with OS is not the `vim` developer used to use, it only has limited functions, so `vim` must be installed mannually.
```shell
$ brew install vim --with-override-system-vi
```
### vim configuration
follow the instruction: [https://github.com/Dogzhou/vim_config](https://github.com/Dogzhou/vim_config)

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

```
$ git config --global core.excludesfile ~/.gitignore_global
```

Edit `~/.gitignore_global`

## Development Environment Setup

### bat
```
brew install bat

# https://github.com/fdellwing/zsh-bat
git clone https://github.com/fdellwing/zsh-bat.git $ZSH_CUSTOM/plugins/zsh-bat
```

### tig
```
$ brew install tig
```

## Command Line Tool

### [autojump](https://github.com/wting/autojump)
autojump provides a faster way to navigate your filesystem

### [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting/blob/master/INSTALL.md)
Fish shell-like syntax highlighting for Zsh

### [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)

### [docker](https://www.docker.com/)

## Softwares
### xcode
install xcode from [app store](https://developer.apple.com/xcode/)

### VSCODE
I personally use [VSCODE](https://code.visualstudio.com/) to do front-end work, it's both lightweight and versatile, configurations and plugins can be uploaded to cloud, which means it's easy to reproduce an identical IDE on a new system. Infrastructure as Code!!

My personal setting locates [here](https://gist.github.com/Dogzhou/70091ca501d339f4cb2c9ea1bcdb585b)

### browsers
No need to say much about [Chrome](https://www.google.com/chrome/) and [firefoxj](https://www.mozilla.org/en-US/firefox/new/), extensions would be sync automatically as soon as login account.

### [Slack](https://slack.com/)

### [Notion](https://www.notion.com/deskto)

### [Dropbox](https://www.dropbox.com)

### [Spectacle](https://www.spectacleapp.com/)
Move and resize windows with ease. Window control with simple and customizable keyboard shortcuts.

### [Balsamiq Mockup 3](https://balsamiq.com/download/)
It's been so fast and easy to do mockup stuff with `Balsamiq Mockup 3`, it provides a cute means with comprehensive widgets, Mockup a web page or mobile can be within minutes.

### [IINA](https://lhc70000.github.io/iina/)
The best video player for macOS ever!!
