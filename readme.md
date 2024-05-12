# Development environment setup

Homebrew: 
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
Oh My ZSH - Z Shell Install:

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

Composer: 
```
brew install composer
```
PHP:
```
brew install php
```
MySQL:
```
brew install mysql
```
Or,
```
brew install mysql@5.7
```
* Bellow command is not mandatory
* 
```
brew link  mysql
```
Or,
```
brew link  mysql@5.7
```
Starting MySQL as service:
```
brew services start mysql
```
or, 
```
brew services start mysql@5.7
```
Valet:
```
composer global require laravel/valet
```
Composer Path:
```
export PATH=$PATH:~/.composer/vendor/bin
```
```
valet install
```
Make a Directory, name as "Sites" or anything else:
```
mkdir Sites
```
Inside the newly created directory "Sites":
```
cd Sites
```
Park the installed valet:
```
valet park
```
Go back to the root directory using the command "~" then:
```
~
```
WP CLI:
```
brew install wp-cli
```
WP Install:
```
https://github.com/wpfresher/wpinstall
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
git config --global user.name "kawsarahmedr"
```
```
git config --global user.email "kawsar.ahmed...@gmail.com"
```

# SSH Generation & Setup Process (GitHub):

SSH References: [Here](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent?platform=mac)

# Generating a new SSH key:

STEP 1: Open the cmd terminal
STEP 2: Paste the text below, replacing the email used in the example with your GitHub email address.
```
ssh-keygen -t ed25519 -C "your_email@gmail.com"
```
CMD Result and Inputs: This creates a new SSH key, using the provided email as a label.
> Generating public/private ALGORITHM key pair.

When you're prompted to "Enter a file in which to save the key", you can press Enter to accept the default file location.
> Enter a file in which to save the key (/Users/YOU/.ssh/id_ALGORITHM): [Press enter]

STEP 3: Type a unique passphrase and remember if for later use. like "kawsarahmed"
> Enter passphrase (empty for no passphrase): [Type a passphrase]

Type the same passphrase again
> Enter same passphrase again: [Type passphrase again]

# Adding your SSH key to the ssh-agent

STEP 1: Start the ssh-agent in the background.
````
eval $(ssh-agent -s)
````
CMD Result:
>Agent pid 1962

STEP 2: If you're using macOS Sierra 10.12.2 or later, you will need to modify your ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in your keychain.

* First, check to see if your ~/.ssh/config file exists in the default location.

````
open ~/.ssh/config
````
CMD Result: The ssh config will open or bellow result.
> The file /Users/YOU/.ssh/config does not exist.

* If the file doesn't exist, create the "config" file. and run the "open ~/.ssh/config" command again.
````
touch ~/.ssh/config
````

* Open your ~/.ssh/config file, then modify the file to contain the following lines. If your SSH key file has a different name or path than the example code, modify the filename or path to match your current setup

````
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
````

STEP 3: 

Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_ed25519 in the command with the name of your private key file.

````
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
````

> Enter passphrase for /Users/YOU/.ssh/id_ed25519:

> Identity added: /Users/YOU/.ssh/id_ed25519 (your_email@gmail.com)

# Add the SSH public key to your account on GitHub.

For more information, see [Adding a new SSH key to your GitHub account.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

STEP 4:

* Check for existing SSH keys. For more information, see [Checking for existing SSH keys.](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)
````
ls -al ~/.ssh
````
Lists the files in your .ssh directory, if they exist

Check the directory listing to see if you already have a public SSH key. By default, the filenames of supported public keys for GitHub are one of the following.

> id_rsa.pub
> 
> id_ecdsa.pub
> 
> id_ed25519.pub

# Adding a new SSH key to your account

SSH: [Adding a new SSH key to your account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

STEP 1: Copy the SSH public key to your clipboard.
````
pbcopy < ~/.ssh/id_ed25519.pub
````
CMD Result:

> Copies the contents of the id_ed25519.pub file to your clipboard

* Tip: If pbcopy isn't working, you can locate the hidden .ssh folder, open the file in your favorite text editor, and copy it to your clipboard.

STEP 2: In the upper-right corner of any page, click your profile photo, then click Settings.

STEP 3: In the "Access" section of the sidebar, click  SSH and GPG keys.

STEP 4: Click New SSH key or Add SSH key.

STEP 5: In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".

STEP 6: Select the type of key, either authentication or signing. For more information about commit signing, see "About commit signature verification."

STEP 7: In the "Key" field, paste your public key.

STEP 8: Click Add SSH key.
