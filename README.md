1. Install vim8.2 with unofficial package
```
sudo add-apt-repository ppa:jonathonf/vim   
sudo apt update
sudo apt install vim

```
2. Install python3 for YouCompleteMe
```
    sudo apt-get install build-essential cmake python-dev python3-dev
```
3. Install [vim-plug](https://github.com/junegunn/vim-plug)
4. Copy the vimrc file and install all the plugins.
5. Config YouCompleteMe server for C/C++ and Go
```
    cd ~/.vim/plugged/YouCompleteMe
    ./install.py --clang-completer --go-completer
    cp ~/.vim/plugged/YouCompleteMe/third_party/ycmd/examples/.ycm_extra_conf.py ~/.vim
```
6. Install [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts). (LeaderF might use it to display special characters). Download a release package, unzip it and use font manger to install fonts on Ubuntu18.04.
```
sudo apt update && sudo apt -y install font-manager
```

7. Install Clang
Add following lines into /etc/apt/sources.list
```
deb http://apt.llvm.org/bionic/ llvm-toolchain-bionic-11 main
deb-src http://apt.llvm.org/bionic/ llvm-toolchain-bionic-11 main
```

Run following commands
```
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
sudo apt update
sudo apt install clang-11 lldb-11 lld-11
sudo apt install libc++-11-dev libc++abi-11-dev
cd /usr/bin
sudo ln -s clang-11 clang
sudo ln -s clang++-11 clang++
```

8. Install ClangFormat
```
sudo apt install clang-format-11
cd /usr/bin
sudo ln -s clang-format-11 clang-format
sudo ln -s clang-format-diff-11 clang-format-diff
```

Generate .clang-format and save it at user home directory.
```
clang-format -style=google -dump-config > ~/.clang-format
```

Change following fields of the .clang-format
```
AccessModifierOffset: -4
IndentWidth:   4

AllowShortEnumsOnASingleLine: false
AllowShortBlocksOnASingleLine: Never
AllowShortFunctionsOnASingleLine: None
AllowShortLambdasOnASingleLine: None
AllowShortIfStatementsOnASingleLine: Never
AllowShortLoopsOnASingleLine: false
```

## Extra links
### [Using Vim to write C++ on Linux](https://www.zhihu.com/question/47691414)
### [install vim8 on Ubuntu16](https://blog.csdn.net/oaix101125/article/details/85019942)
### [install GTags](https://zhuanlan.zhihu.com/p/36279445)
### [ClangFormat](http://clang.llvm.org/docs/ClangFormat.html)


