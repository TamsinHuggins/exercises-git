# 🐙 Git & GitHub Workshop — Part 2: Setting up a Remote Repo

---

## Section 1 - Create a GitHub Account and Repository

### Step 1 - Sign up to GitHub

If you don't already have a GitHub account, head to [github.com](https://github.com) and sign up for a free account.

> 💡 Use a **personal email address**, not a company one.

---

### Step 2 - Create a new repository

1. Click the **+** icon in the top-right corner and select **New repository**
2. Give it a unique name. You could use **git-practice** as you will be linking this with the local repo you created in Part 1.
3. Set the visibility to **Public**
4. Leave the following **unchecked** for now:
   - ❌ Add a README file
   - ❌ Add .gitignore
5. Click **Create repository**

> 💡 We will leave those options unchecked because we already have a local repo with history. Adding them here would create a conflict when we try to link the two.

---

## Section 2 - Link your Local Repo to GitHub

GitHub will show you instructions for linking a local repo. You have two options:

| Option | When to use |
|---|---|
| Create a new local repo | Starting from scratch |
| Link an existing local repo | You already have a local repo ✅ |

We'll use the second option — linking the **git_practice** repo we created in Part 1.

---

### Step 1 - Set `origin` to point to your remote repo

This creates the "bridge" between your local repository and GitHub. After running this, `origin` is the alias that holds your remote repo URL.

```
git remote add origin [your repo URL]
```

---

### Step 2 - Rename your branch to `main`

Git's default branch was historically called `master`, but the modern convention (and GitHub's default) is `main`.

```
git branch -M main
```

---

### Step 3 - Push your local commits to GitHub

```
git push -u origin main
```

> 💡 The `-u` flag sets `origin main` as the **upstream** for your local `main` branch. After this first push, you can simply run `git push` in future without specifying the branch name.

---

### 🔍 Useful: Check your remote connection

To verify that `origin` is pointing to the right place:

```
git remote show origin
```

---

## Section 3 - Practising a Real Developer Workflow

In a professional team, developers rarely commit directly to `main`. Instead, each piece of work (a feature, a bug fix, a small improvement) lives on its own **branch**. This keeps `main` stable and gives the team a chance to review changes before they are merged.

Here is a simple version of that workflow to practise.

---

### Step 1 - Create and switch to a new branch

Rather than working directly on `main`, create a new branch for your change. This keeps your work isolated until it is ready to be reviewed.

```
git checkout -b feature/my-first-feature
```

> 💡 The `-b` flag creates the branch and switches to it in one step. Naming branches with a prefix like `feature/` or `fix/` is a common convention that helps teams understand the purpose of the branch at a glance.

---

### Step 2 - Make a change and commit it

Make a small change — for example, edit your `README.md` to add a line of text.

Then stage and commit your change:

```
git add .
git commit -m "Add a line to README from feature branch"
```

> 💡 In a dev team, each commit should represent one logical change with a clear message. Good commit messages help teammates (and future you) understand the history of the project without having to read every line of code.

---

### Step 3 - Push your branch to the remote

Push your new branch up to GitHub. The first time you push a new branch, you need to tell Git where to push it:

```
git push -u origin feature/my-first-feature
```

> 💡 This creates the branch on the remote too. After this, `git push` alone is enough for future pushes on this branch. In a team, pushing your branch to the remote also acts as a backup and lets others see your work in progress.

---

### Step 4 - Open a Pull Request on GitHub

Go to your repository on GitHub. You should see a prompt to **"Compare & pull request"** for your recently pushed branch.

A **Pull Request (PR)** is a formal way of saying: *"I have made some changes on my branch — I would like these to be reviewed and merged into `main`."*

1. Click **Compare & pull request**
2. Give your PR a clear title and a short description of what you changed and why
3. Click **Create pull request**

> 💡 In a dev team, PRs are where code review happens. A colleague can read your changes, leave comments, request improvements, and eventually **approve** the PR. This process catches bugs early and keeps code quality high before anything reaches `main`.

---

### Step 5 - Merge the Pull Request

Once the PR is approved (in this case, you can approve your own for practice), click **Merge pull request** on GitHub.

> 💡 After merging, it is good practice to delete the feature branch — it has done its job. GitHub will offer this option immediately after merging.

---

### Step 6 - Pull the merged changes back to your local `main`

Switch back to your local `main` branch and pull down the merged changes:

```
git checkout main
git pull origin main
```

> 💡 This keeps your local `main` in sync with the remote. In a team, you would do this regularly so your local repo does not fall behind the shared codebase.

