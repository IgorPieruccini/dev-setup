# dev-setup
My step by step instruction on how to set my dev setup

## Installation

### Curl
```bash
    sudo apt install curl
```

### Git
```bash
    sudo apt install git-all
```

### Xclip
```bash
    sudo apt install xclip
```

### Brew
```bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)
```
Please follow the instruction given by the installation guide after run the command

### Node
```bash
    brew install node
```

### reipgrep
```bash
    brew install ripgrep
```
For telescope to work properly, you need to install ripgrep

### NeoVim
```bash
    brew install neovim
```

### Tmux
```bash
brew install tmux
```
## Generate SSH Key
```bash
	ssh-keygen -t ed25519 -C "your_email@example.com"
```
## Add SSH Key to SSH Agent
```bash
	add ssh to git
```

## Neovim configuration

### Clone the repository
```bash
    git clone git@github.com:IgorPieruccini/nvim.git
```
Make sure to clone inside the ~/.config folder

Run 
```bash
    nvim 
```

inside the nvim folder and run the command
```bash
    :PlugInstall
```

Install the LSP and other dependencies with Mason
```bash
    :Mason
```

To have cool icons install a font from nerdfonts
[Nerdfonts](https://www.nerdfonts.com/font-downloads)

Now it's a good moment to run :checkhealth and see if everything is working properly

## Configure Bash
```bash
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}

PS1_wdir="\[$(tput sgr0)\]\[\033[38;5;24m\]\W"
PS1_gitbranch="\e[38;5;204m\]\$(parse_git_branch)"
PS1_gt="\[$(tput bold)\]\[$(tput sgr0)\]\[\e[38;5;214m\]>"
PS1_other="\[$(tput sgr0)\]\[$(tput sgr0)\]\[\e[38;5;15m\]"

export PS1="${PS1_wdir}${PS1_gitbranch}${PS1_gt}${PS1_other} \[$(tput sgr0)\]"
```

## Configure Tmux
Create the conf file at ~/.tmux.conf
The content of the file you can find in this repository [here](./tmux.conf)

Install the tmux plugin manager by cloning the repository
```bash
    git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Add tmuxifier by cloning the repository
```bash
    git clone https://github.com/jimeh/tmuxifier.git ~/.tmuxifier
```
now open your ~/.bashrc or ~/.zshrc or ~/.profile  and add the following line
```bash
    export PATH="$HOME/.tmuxifier/bin:$PATH"
    eval `tmuxifier init -`
```

## Configure i3 Tile management window

### Install i3
```bash
    sudo apt install i3
```

Start i3:
    Log out of your current session.
    On the login screen, select i3 from the session menu.
    Log back in.

Initial Configuration:
    The first time you log in, i3 will prompt you to create a configuration file. Follow the prompts to create it.

Edit Configuration File:
    The configuration file is located at ~/.config/i3/config. You can edit it with your favorite text editor to customize i3.



Happy coding!


## tips

### using i3

Set keyboard layout

Copy the content from [i3 config](./i3/config) and paste it in the i3 config file of your system

for setting up the background image you need to install feh
```bash
    sudo apt install feh
```

To have a nice bar you can install polybar
```bash
    sudo apt install polybar 
```

To config i3 paste the content of [polybar init]](./polybar/config.ini)
to ~/.config/polybar/config.ini

and to correct load polybar at startup paste the content of [polybar launch](./polybar/launch_polibar.sh.sh)
to ~/.config/polybar/launch_polibar.sh.sh

Happy coding!
