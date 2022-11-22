# Solutions

Solutions to all sorts of annoying problems. Ranges from common to rare. I can’t seem to remember these solutions sometimes too..

## Table of contents

Maybe ill organize this better later. Or even make it a website.

## Fix npm requires root access to install modules

Use nvm. It's that simple.  

Uninstall Nodejs and NPM  

Then install NVM - [NVM install and update instructions](https://github.com/nvm-sh/nvm#installing-and-updating)  

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

# or

wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

Dont forget to restart your terminal or run `source ~/.bashrc`  

Then install node using NVM

```bash
nvm install node
```

## Create GitHub repo from command line in a folder and push it

_Yeah I know, I dont know how to use git._  

If you get a permission denied error when trying to push to the repo, you may need to create a new ssh key and add it to your GitHub account.

```bash
ssh-keygen -t ed25519 -C 'your_email@example.com"
```

Copy the entire contents of the saved file (it should have listed it after you executed the command).  
Go to your GitHub Account Settings > SSH and GPG Keys > and create a new SSH key. Give it a name and set it to `Authentication` then paste the file contents into the ssh key feild.
> Source <https://stackoverflow.com/a/57734732>  

### Mac

Install github cli

```bash
brew install gh
```

Create github repo. A `--public`, `--private` or `--internal` flag is required.

```bash
gh repo create <name> [flags]
```

Init Repo

```bash
git remote add origin <repo_url>
git push -u origin master
```

## System Dark Mode Not Working On Chrome on Ubuntu?

Ubuntu 22.04 is the os I had this problem on.  
Heres a fix.

[Credits To This Article](https://dev.to/ankitbrijwasi/enable-dark-mode-in-chrome-on-ubuntu-20na)

Run gedit (or preferred text editor; nano, vscode, vim, ...)

```bash
sudo gedit /usr/share/applications/google-chrome.desktop
```

Find the line that has

```bash
Exec=/usr/bin/google-chrome-stable %U
```

And replace it with

```bash
Exec=/usr/bin/google-chrome-stable %U --enable-features=WebUIDarkMode --force-dark-mode
```

Then find the line that has

```bash
Exec=/usr/bin/google-chrome-stable
```

And replace it with

```bash
Exec=/usr/bin/google-chrome-stable --enable-features=WebUIDarkMode --force-dark-mode
```

Restart Chrome and it should be dark mode.

## _Actually_ Installing Ubuntu (or Any Linux(?) OS) Onto A USB

This goes over how to install Ubuntu onto a USB, making it essentially a portable OS.

### Using a VirtualBox Virtual Machine

Install VirtualBox from [here](https://www.virtualbox.org/wiki/Downloads).  
Download the `.iso` of [Ubuntu Desktop](https://ubuntu.com/download/desktop) or any other Linux distro of your choosing.  

Add your user to the `vboxusers` group. This is required to be able to use USB devices in VirtualBox.

```bash
sudo usermod -a -G vboxusers $USER
```

Reboot your system.

**TODO** Add creating the virtual machine instructions here...

Start the virtual machine, then follow these [instructions](#steps).

### Using Another USB Installer

(I have not tested this but it should be the same as using the vm)

### Steps

Steps go here. TODO

gparted  
install  
dont reboot  
copy boot and efi  
...  

## Make password entry in terminal display feedback (*'s)

```bash
sudo visudo
```

Find

```bash
Defaults    env_reset
```

Make it look like

```bash
Defaults    env_reset,pwfeedback
```

`Ctrl + X` to save and exit. `Y` to confirm and `Enter` to finish.
