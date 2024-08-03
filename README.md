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

Happy coding!
