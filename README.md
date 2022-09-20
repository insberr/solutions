# solutions
Solutions to all sorts of annoying problems. Ranges from common to rare. I can’t seem to remember these solutions sometimes too..


## Fix npm requires root access to install modules
Use nvm. It's that simple.

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
