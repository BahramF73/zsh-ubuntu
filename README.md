# zsh-ubuntu
Install ZSH (Z Shell), PowerLevel10K, zsh-syntax-highlighting, zsh-autosuggestions and command-not-found plugins on Ubuntu


Commands I used:

#install git:
sudo apt install git

#install zsh and switch from bash to zsh:
sudo apt install zsh
chsh -s $(which zsh)

#install zsh-autosuggestions:
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/zsh-autosuggestions
echo 'source ~/.zsh/zsh-autosuggestions/zsh-autosuggestions.zsh' >>~/.zshrc

#install zsh-syntax-highlighting:
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git
echo 'source ~/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh' >>~/.zshrc

#install powerlevel10k:
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
