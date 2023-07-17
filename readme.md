# dev-env-setup

Xcode:
```
xcode-select --install
```
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
https://github.com/relevenx/wpinstall
```
Node: 
```
brew install node
```
Git: 
```
brew install git
```
- Create ssh key for git: [follow this guide](https://docs.tritondatacenter.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-mac-os-x)
