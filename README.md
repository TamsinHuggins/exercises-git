# Section 1 - Committing changes

## git status

```
mkdir git_practice
cd git_practice
pwd
Ls
ls -a
```

We have created a new, empty directory called git_practice.

```
git status

```

You should a message like:

```
fatal: not a git repository (or any of the parent directories): .git
```

This means we are not inside a git repository. git_practise is just a regular directory/folder. It has no git repository (yet)

## git init

Initialise a git repository to track the files in the git_practice folder

```
git init
```

Check the status again

```
Git status
```

You will see a response like

```

On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)

```

### What is git_practice?

- It was just a folder/directory on your machine

- It is now git tracked

- You can call it the `working directory` or `local repository (local repo)`

- Changes you make inside git_practise folder are tracked by git

![alt text](image-1.png)

### Create a new file inside git_practice called greetings.txt

```
touch greetings.txt
ls
```

You shouldsee that git_practice folder now contains a plain text file called greetings.txt

![alt text](image-2.png)

Now that git_practice is a git repository, its contents are being tracked.

![alt text](image-6.png)

### What is an untracked file?

In your terminal, check the status of the git repository

```
git status

```

You should see the status of your repository, which will include your greetings.txt file showing up as "untracked"

![alt text](image-4.png)

In Git, an untracked file is a file that exists in your working directory but is not yet part of your repository. This means Git is not tracking changes to it.

## git add

To start tracking greetings.txt, you use the `git add` command.

```
git add greetings.txt
git status
```

This adds greetings.txt to the staging area.

![alt text](image-5.png)

### What is the Staging Area?

The staging area in Git is a space where you can organize and review changes before committing them to the repository. It allows you to selectively stage specific changes, providing greater control over what gets included in your next commit.

The git add command adds **changes** to the staging area. This includes new files, modifications, and deletions, preparing them to be included in the next commit.

## git commit

```
git commit -m "initial commit, empty greeetings text file created"

```

### Commiting modifications

### Type your first greeting in greetings.txt

![alt text](image-3.png)

When you modify a tracked file, Git knows about it.

When you do a `git status`, Git says the changes are not yet staged for commit
i.e. you haven't said you're ready to commit the modification

```
git status

```

## End of section challenge

Create a new file in git_practice called goodbyes.txt
Add to goodbyes.txt the word for goodbye in your chosen language.
This time, instead of adding just one file or change to the staging area, try adding all changes to the staging area using `.` to mean everything

```
git add .
```

Check the status to see what has been staged
Commit these changes to the repository with a suitable commit message

## Section 2 - Branching
