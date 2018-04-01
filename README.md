# EMac
EMac is to describe for my daily-used softwares, as well as configurations and preference on MacOS

## Update OS related package
1. Update operate system to the latest version
2. brew update

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

Edit `~/.gitignore_global`(blow is my personal one)
```shell
# Compiled source #
###################
*.com
*.class
*.dll
*.exe
*.o
*.so

# Packages #
############
# it's better to unpack these files and commit the raw source
# git has its own built in compression methods
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip

# Logs and databases #
######################
*.log
*.sql
*.sqlite

# OS generated files #
######################
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

# IDE
.idea
*.swp
*.swo

# rails
.byebug_history
```
