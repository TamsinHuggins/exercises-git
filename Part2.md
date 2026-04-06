# Git & GitHub Workshop Part 2 - Setting up a Remote Repo


## Section 1 - Create a GitHub account and create a new repository.
If you don't have a GitHub account, go to github.com and sign up for a free account. Use a personal email address, not a company one.

Create a public repository and give it a unique name. Uncheck "add a README file" and "add .gitignore" for now.

## Section 2 - Link your local repo to the remote repo on GitHub

GitHub will give you instructions for linking a local repo to this new remote repo. You have two options:
- create a new local repository  ( if you are starting from scratch), or
- link an existing local repository ( if you have an existing local repo)

Let's use the git_practice repository we created in Part 1 as our existing local repository.

Inside your local repo for git_practice, you can run the code given by GitHub. The lines are explained below:

Set "origin" to create the "bridge" that links your local repository to the remote repository on GitHub. 
Once you have run this command, origin will point to the URL of the remote repo. 
This links your local repo to the remote repo on GitHub. You will then be able to push and pull changes between the two repos.

```
git remote add origin [your repo URL]
```

Switch branch to main (instead of master).

```
git branch -M main
```

Push local commits to the remote repo. This pushes the changes you have made in your local repo to the remote repo on GitHub. 
The -u flag sets the upstream for the main branch, which means that in future you could run git push without specifying the branch name.
```
git push -u origin main
```
