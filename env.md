# Development Environment Checklist
This guide assumes you are reasonably familiar with basic shell commands and know how to use `vim`.

## Ubuntu

### Install the [Homebrew](https://brew.sh/) package manager
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
You'll want to follow the post-install steps recommended by the install script, e.g.
```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/bits/.zprofile
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
brew install gcc
```

### Install the [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) `zsh` plugin manager 
```bash
echo 'source $HOME/.zshrc' >> /home/bits/.zprofile
zsh
```

### Install the [Powerlevel10k](https://github.com/romkatv/powerlevel10k) `zsh` theme
```zsh
vi ~/.zshrc 
### set ZSH_THEME="powerlevel10k/powerlevel10k"
source ~/.zshrc
```
Run through prompt; if symbols look strange, install the [suggested font](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k).

### Configure shell syntax highlighting
```zsh
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

### Configure shell autocompletion
```zsh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

### Use `vim` commands in the terminal
```zsh
git clone https://github.com/jeffreytse/zsh-vi-mode $ZSH_CUSTOM/plugins/zsh-vi-mode
```

### Enable fuzzy search via [fzf](https://github.com/junegunn/fzf)
```zsh
brew install fzf
```
Follow the post-install steps recommended by the install script, e.g.
```zsh
/home/linuxbrew/.linuxbrew/opt/fzf/install
```

You'll also want the [fzf-tab](https://github.com/Aloxaf/fzf-tab) plugin for `zsh`:
```zsh
git clone https://github.com/Aloxaf/fzf-tab $ZSH_CUSTOM/plugins/fzf-tab
```

### Enable `zsh` plugins
```zsh
vi ~/.zshrc
### set plugins=(git zsh-syntax-highlighting zsh-autosuggestions fzf fzf-tab zsh-vi-mode)
source ~/.zshrc
```

### Install [lsd](https://github.com/Peltoche/lsd)
```zsh
brew install lsd
echo "alias ls='lsd'" >> ~/.zshrc
```

### Set up `git`
```zsh
git config --global user.name "your name goes here"
git config --global user.email "your email goes here"
git config --global push.autoSetupRemote true
git config --global core.editor "vim"
```

### Configure `vim`
```zsh
echo "syntax on" >> ~/.vimrc
echo "set re=0" >> ~/.vimrc
echo "set autoindent expandtab tabstop=2 shiftwidth=2" >> ~/.vimrc
```
