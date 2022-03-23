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

### Install [`powerlevel10k`](https://github.com/romkatv/powerlevel10k):
```
 git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
 echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```


## Uninstallation

### Uninstall [`powerlevel10k`](https://github.com/romkatv/powerlevel10k):

1. Remove all references to "p10k" from `~/.zshrc`. You might have this snippet at the top:
   ```zsh
   if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
     source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
   fi
   ```
   And this at the bottom:
   ```zsh
   [[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh
   ```
   These are added by the [configuration wizard](#configuration-wizard). Remove them.
2. Remove all references to "powerlevel10k" from `~/.zshrc`, `~/.zpreztorc` and `~/.zimrc` (some
   of these files may be missing -- this is normal). These references have been added manually by
   yourself when installing Powerlevel10k. Refer to the [installation instructions](#installation)
   if you need a reminder.
3. Verify that all references to "p10k" and "powerlevel10k" are gone from `~/.zshrc`, `~/.zpreztorc`
   and `~/.zimrc`.
   ```zsh
   grep -E 'p10k|powerlevel10k' ~/.zshrc ~/.zpreztorc ~/.zimrc 2>/dev/null
   ```
   If this command produces output, there are still references to "p10k" or "powerlevel10k". You
   need to remove them.
4. Delete Powerlevel10k configuration file. This file is created by the
   [configuration wizard](#configuration-wizard) and may contain manual edits by yourself.
   ```zsh
   rm -f ~/.p10k.zsh
   ```
5. Delete Powerlevel10k source files. These files have been downloaded when you've installed
   Powerlevel10k.
   
   `rm -rf ~/powerlevel10k`

6. Restart Zsh. [Do not use `source ~/.zshrc`](#weird-things-happen-after-typing-source-zshrc).
7. Delete Powerlevel10k cache files.
   ```zsh
   rm -rf -- "${XDG_CACHE_HOME:-$HOME/.cache}"/p10k-*(N) "${XDG_CACHE_HOME:-$HOME/.cache}"/gitstatus
   ```
