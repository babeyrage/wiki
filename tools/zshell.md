# Z Shell
Z shell (Zsh) is a Unix shell that can be used as an interactive login shell and as a command interpreter for shell scripting. Zsh is an extended Bourne shell with many improvements, including some features of Bash, ksh, and tcsh.

Documentation:

## Installation

### Linux

1. Install latest version
```
sudo apt-get update
sudo apt-get install zsh
```

2. To check whether you have installed zsh correctly or not by 
```
zsh --version
```

Installing ZSH will not modify and set it as the default shell. We have to modify the settings to make ZSH our default shell.
```
chsh -s /usr/bin/zsh
```

Reload ssh connection to load zsh. Once it loads, select option "0" to create .zshrc file and then copy custom .zshrc
