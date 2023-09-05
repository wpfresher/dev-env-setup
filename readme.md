# Development environment setup

Homebrew: 
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Composer: 
```
brew install composer
```
Composer Path:
```
export PATH=$PATH:~/.composer/vendor/bin
```
PHP:
```
brew install php
```
MySQL:
```
brew install mysql@5.7
```
```
brew link  mysql@5.7
```
```
brew services start mysql@5.7
```
Valet:
```
composer global require laravel/valet
```
```
valet install
```
```
valet park
```
WP CLI:
```
brew install wp-cli
```
WP Install:
```
https://github.com/bappi/wpinstall
```
Node: 
```
brew install node
```
Git: 
```
brew install git
```
Github CLI:
```
brew install gh
```
Git Config:
```
git config --global user.name "bappi"
git config --global user.email "bappi.cs@gmail.com"
```
SSH: [Here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=mac)
