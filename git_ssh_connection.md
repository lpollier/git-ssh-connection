# Git SSH connection:


## 1. Checking for existing SSH keys:

* Linux/Windows:

`$ ls -al ~/.ssh` # Lists the files in your .ssh directory, if they exist

Source: https://help.github.com/articles/checking-for-existing-ssh-keys/


## 2. Generating a new SSH key and adding it to the ssh-agent:

* Linux/Windows:

`$ ssh-keygen -t rsa -b 4096 -C "email@address.com"`

`$ eval "$(ssh-agent -s)"` # Start the ssh-agent in the background

`$ ssh-add ~/.ssh/id_rsa` # Add your SSH private key to the ssh-agent

Source: https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/


## 3. Adding a new SSH key to your GitHub account:

* Linux:

`$ sudo apt-get install xclip` # Downloads and installs xclip. If you don't have `apt-get`, you might need to use another installer (like `yum`)

`$ xclip -sel clip < ~/.ssh/id_rsa.pub` # Copies the contents of the id_rsa.pub file to your clipboard

* Windows:

`$ clip < ~/.ssh/id_rsa.pub` # Copies the contents of the id_rsa.pub file to your clipboard

Source: https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/


## 4. Testing your SSH connection:

* Linux/Windows:

`$ ssh -T git@github.com` # Attempts to ssh to GitHub

Source: https://help.github.com/articles/testing-your-ssh-connection/
