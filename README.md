# EMac
EMac is to describe for my daily-used softwares, as well as configurations and preferrecnes on MacOS

## Update OS related package
1. Update operate system to the latest version
2. brew update

## Terminal
[ITerm](https://www.iterm2.com/)

## Shell
[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)

configurations in `~/.zshrc`
```
ZSH_THEME="arrow"
export EDITOR='vim'
plugins=(git ruby rails autojump docker encode64 bundler zsh-autosuggestions)
```

## IDE
the built-in `vi` with OS is not the `vim` programmer used to use, it only has limited functions, so `vim` must be installed mannually.
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
```
alias ctags="`brew --prefix`/bin/ctags"
```
