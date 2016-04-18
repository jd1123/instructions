# This is a document intended to explain how to set up golang in arch with VIM as the IDE. Let's begin.


* Install the necessary packages:

Before we begin, we need to install the software! This is pretty easy:

```
sudo pacman -S go vim tmux
```

Edit your GOPATH, GOROOT etc in your .zshrc file:

```
export GOPATH=$HOME/Documents/dev/go
export GOROOT=/usr/lib/go
export PATH=$PATH:$GOPATH/bin

```

* Install Vundle for vim:

This will manage the bundles for vim. Go [here](https://github.com/VundleVim/Vundle.vim) and follow the instructions. Pretty simple. 

* Set up Vim:

Add the following to your .vimrc file so that you get nice sane defaults:

```
set tabstop=4
set shiftwidth=4
set softtabstop=4
set nu
```

* Install Vim plugins:

You'll need to install golang vim bundles to make life nice and easy:

[Vim Fugitive](https://github.com/tpope/vim-fugitive)
[Nerd Tree](https://github.com/scrooloose/nerdtree)
[Vim-go](https://github.com/fatih/vim-go)
[Syntastic](https://github.com/scrooloose/syntastic)

* Set up zsh (or bash if you prefer) to use project specific GOPATHs:

I like to have project specific GOPATHs, as it makes dependencies nice and easy. There is a pretty good way of doing this thanks to [Herbert G. Fisher](http://hgfischer.org/article/managing-multiple-gopaths/). It works like this - you will add a blank file called .gopath to the directory that you want to be your GOPATH, and you will edit your .zshrc file to check for these on changing directory. You need to add the folling snippet to your .zshrc:

```
cd () {
    builtin cd "$@"
    cdir=$PWD
    while [ "$cdir" != "/" ]; do
        if [ -e "$cdir/.gopath" ]; then
            export GOPATH=$cdir
            break
        fi
        cdir=$(dirname "$cdir")
    done
}
```

* Start coding and stop messing around:

That's it! You should have a nice working IDE within vim for writing go code. 
