
# Adding locally hosted code to GitHub

If you have existing source code or repositories stored locally on your computer or private network you can add them to GitHub by typing commands in a terminal. You can do this by typing Git commands directly, or by using GitHub CLI.



```bash
Warning: Never git add, commit, or push sensitive information to a remote repository. Sensitive information can include, but is not limited to:

Passwords
SSH keys
AWS access keys
API keys
Credit card numbers
PIN numbers

```


## Installation

Adding a local repository to GitHub with GitHub CLI.

In the command line, navigate to the root directory of your project.

Initialize the local directory as a Git repository.

```bash
  git init -b main
```

Stage and commit all the files in your project
```bash
git add . && git commit -m "initial commit"
```  
To create a repository for your project on GitHub, use the gh repo create subcommand. When prompted, select Push an existing local repository to GitHub and enter the desired name for your repository. If you want your project to belong to an organization instead of your user account, specify the organization name and project name with organization-name/project-name.

Follow the interactive prompts. To add the remote and push the repository, confirm yes when asked to add the remote and push the commits to the current branch.

Alternatively, to skip all the prompts, supply the path to the repository with the --source flag and pass a visibility flag (--public, --private, or --internal). For example, gh repo create --source=. --public. Specify a remote with the --remote flag. To push your commits, pass the --push flag. For more information about possible arguments, 
[GitHub CLI manual.](https://cli.github.com/manual/gh_repo_create)

## Adding a local repository to GitHub using Git
Create a new repository on GitHub.com. To avoid errors, do not initialize the new repository with README, license, or gitignore files. You can add these files after your project has been pushed to GitHub.

Open Terminal.

Change the current working directory to your local project.

Initialize the local directory as a Git repository.
```bash
$ git init -b main
```
Add the files in your new local repository. This stages them for the first commit.
```bash
$ git add .
# Adds the files in the local repository and stages them for commit. To unstage a file, use 'git reset HEAD YOUR-FILE'.
```
Commit the files that you've staged in your local repository.
```bash
$ git commit -m "First commit"
# Commits the tracked changes and prepares them to be pushed to a remote repository. To remove this commit and modify the file, use 'git reset --soft HEAD~1' and commit and add the file again.
```
At the top of your repository on GitHub.com's Quick Setup page, click  to copy the remote repository URL.

In Terminal, add the URL for the remote repository where your local repository will be pushed.
```bash
$ git remote add origin  <REMOTE_URL> 
# Sets the new remote
$ git remote -v
# Verifies the new remote URL
```

Push the changes in your local repository to GitHub.com.
```bash
$ git push -u origin main
# Pushes the changes in your local repository up to the remote repository you specified as the origin
```

How do I properly force a Git push?
```bash
git push origin <your_branch_name> --force
```
or if you have a specific repo:
```bash
git push origin <your_branch_name> --force
git push https://git.... --force

This will delete your previous commit(s) and push your current one.

It may not be proper, but if anyone stumbles upon this page, thought they might want a simple solution...
```
*********************************

## Git push existing repo to a new and different remote repo server?

```bash
Create a new repo at github.
Clone the repo from fedorahosted to your local machine.
git remote rename origin upstream
git remote add origin URL_TO_GITHUB_REPO
git push origin master
```
Now you can work with it just like any other github repo. To pull in patches from upstream, simply run ```bash git pull upstream master && git push origin master. ```
