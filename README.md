# Ubuntu ZSH
Install ZSH (Z Shell), PowerLevel10K, zsh-syntax-highlighting, zsh-autosuggestions and command-not-found plugins on Ubuntu

## Installation

### Install `git`:
```
 sudo apt install git
```

### Install `zsh` and switch from `bash` to `zsh`:
```
 sudo apt install zsh
 chsh -s $(which zsh)
```
 
### Install `zsh-autosuggestions`:
```
 git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
 echo 'source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh' >>~/.zshrc
```

### Install `zsh-syntax-highlighting`:
```
 git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
 echo 'source ~/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh' >>~/.zshrc
```

### Install `powerlevel10k`:
```
 git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
 echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```
