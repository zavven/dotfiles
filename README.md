Zack's Mac Profile & Software
===============================

## Xcode

安装 Xcode command line tools, 运行：

```sh
xcode-select --install
```

## Homebrew

安装 Homebrew 运行：

```sh
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### 替换USTC镜像
参考中科大的[使用文档](http://mirrors.ustc.edu.cn/help/brew.git.html)

```sh
# Homebrew 源
cd "$(brew --repo)"
git remote set-url origin https://mirrors.ustc.edu.cn/brew.git

# Homebrew Bottles 源
echo 'export HOMEBREW_BOTTLE_DOMAIN=https://mirrors.ustc.edu.cn/homebrew-bottles' >> ~/.zshrc
source ~/.zshrc

# Homebrew Core 源
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-core.git

# Homebrew Cask 源
cd "$(brew --repo)"/Library/Taps/caskroom/homebrew-cask
git remote set-url origin https://mirrors.ustc.edu.cn/homebrew-cask.git
```

## Install By Homebrew

```sh
brew install git tig
brew install zsh zsh-completions
# brew install autojump // z 替代 autojump
brew install stow
brew install hub
brew install tmux
brew install vim --with-lua --with-override-system-vi
brew install nvm
```

## Install By Homebrew Cask

```sh
brew cask install iterm2
brew cask install google-chrome
brew cask install firefox
brew cask install android-studio
brew cask install macdown
brew cask install cheatsheet
brew cask install alfred
brew cask install java
brew cask install sublime-text
brew cask install webstorm
```

## 创建大小写敏感的工作区

```sh
hdiutil create -type SPARSE -fs 'Case-sensitive Journaled HFS+' -size 100g -volname workspace ~/Documents/workspace.dmg.sparseimage
```

## oh-my-zsh

安装 oh-my-zsh 运行：

```sh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## 创建 SSH Key

https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

```sh
# new a ssh-key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

Start the ssh-agent in the background.

```sh
eval "$(ssh-agent -s)"
```

If you're using macOS Sierra 10.12.2 or later, you will need to modify your ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in your keychain.

```
Host *
 AddKeysToAgent yes
 UseKeychain yes
 IdentityFile ~/.ssh/id_rsa
```

Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.

```sh
ssh-add -K ~/.ssh/id_rsa
```

## nvm 设置

使用 Homebrew 安装 nvm 之后，运行：

```
echo '# nvm\nexport NVM_DIR="$HOME/.nvm"\n. "/usr/local/opt/nvm/nvm.sh"' >> ~/.zshrc
echo 'export NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node' >> ~/.zshrc
```

## Git 设置
```
git config --global alias.up 'pull --rebase --autostash'
```
