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

Then install node using NVM
```bash
nvm install node
```


## Create GitHub repo from command line in a folder and push it.
_Yeah I know, I dont know how to use git._  

If you get a permission denied error when trying to push to the repo, you may need to create a new ssh key and add it to your GitHub account.

```bash
ssh-keygen -t ed25519 -C 'your_email@example.com"
```
Copy the entire contents of the saved file (it should have listed it after you executed the command).  
Go to your GitHub Account Settings > SSH and GPG Keys > and create a new SSH key. Give it a name and set it to `Authentication` then paste the file contents into the ssh key feild.
> Source https://stackoverflow.com/a/57734732  

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
