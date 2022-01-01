---
marp : true
footer: '![height:60px](./assets/logo_banner_black.png)'
---
<style>
section {
  backgroundColor: #AAAAAA;
  font-family: 'JetBrains Mono';
  text-align: justify;
}
footer {
  right: 30px;
  text-align: right;
}
h2, h3 {
    font-weight: bolder;
}
img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
</style>

# Git Class

---

## What exactly is Git ?

---

- Created by Linus Torvalds in 2005
- Version Control System (VCS)
  - Mainly used for tracking changes in file in a project
  - Nowadays used for doing collaboration work
- **Git and GitHub have different purpose !**
  - GitHub are a place to **host a project**, which are **maintained using Git**
  - GitHub also offers more feature than a plain Git

---

## Benefits of using Git

- Track project changes
- Ability to recover to old state when something is broken
- Collaborative programming

---

## Setting Up Git

Make sure that you already created your GitHub account

```bash
git config --global user.name "<YOUR_NAME>"
git config --global user.email "<YOUR_EMAIL>"
```

---

## Git Repositories

A directory which every files and folders inside it are tracked by Git

### Creating a repository

```bash
# Create folder and enter folder
mkdir <FOLDER_NAME> && cd <FOLDER_NAME>

# Initialize Git repo
git init .   # The . character means current directory
```

You can use `git status` to check your current Git repository

---

### Check for a change in your Git repo

After adding a file, you can check for any change using `git status`.

Any new file that is added will not be tracked by default. To start tracking for any particular file / folder, use `git add <FILE/FOLDER_NAME>`

> `git add` command also send your change to the *staging area*. A staging area is a place to gather all your change that are ready to be *committed*

---

## Git Commit

> A commit is like a *checkpoint* for your project. In between two timestamp, a commit record any changes that you had made, including other details like the person who made the change or the message explaining the changes.

After adding your changes in the staging area, you can use `git commit` to create a new commit.

---

Git default editor will fire up. The editor depends on what you choose during installation, but the content will be look like this:

```gitcommit
<CURSOR_HERE>
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch master
#
# Initial commit
#
# Changes to be committed:
#       <ANY_OF_YOUR_CHANGES>
...

```

---

### Commit Message Structure

```gitcommit
<COMMIT_TITLE>

<COMMIT_MESSAGE>
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
...

```

You can also use `git commit -m "<COMMIT_MESSAGE>"` if you just want some short commit message.

---

## Git Log and Git Show

If you want to see a list of your commit history, you can use `git log`. Wanna see the details of the previous log ? Use `git show <COMMIT_HASH>`

> Pro Tip : You don't need to type all those long commit hash. You just need to type the first 3-4 character in the commit hash and let the *tab completion* do the rest. Of course, it's still better to use plugin in your code editor

---

## Pause Here

Now let's move to GitHub

---

## Connecting to GitHub

Since August, GitHub disabled the password authentification on command line. Now, there are two options for authentification which we will cover both here.

---

## Method 1: GitHub Token

From your GitHub, follow this step:

```bash
Settings -> Developer Settings -> Personal Access Tokens -> Generate New Tokens
```

- For ease of use, set token expiration to `No Expiration` 
- The scope that are used for pushing commit are the `repo` scope

After clicking the *Generate Token* button, you will get your token as a replacement for password.

---

You might be bothered to enter such a random token each time you push. Here's an (**unsafe**) solution. You can choose to store your token locally, but your token will not be encrypted (hence the danger).

```bash
# Store GitHub token locally
git config --global credential.helper store
```

---

## Method 2: (Windows-only) Use Credential Manager

```bash
# Use the provided credential helper from Git for Windows package
git config --global credential.helper manager-core
```

After setting this, when you push your commit, a window will open and ask you to login to GitHub. Follow the instructions and you're done.

---

There are still more method to use like SSH agent (I use this) or other custom credential helper. But we won't cover it here.

---

## Pushing Repository to GitHub

---

What you have earlier is what usually called ***local repository***. The repository on your GitHub is usually called ***remote repository***.

> The term *remote* means that the repository is hosted somewhere (not in your computer). Remote repository also enable others to contribute to the project

Now let's create our remote repository, to then connect it to our local repo

---

Now you have your remote repository URL. Now, we can connect our local repository with the remote repository using the provided URL

```bash
# Run this inside your local repo directory !
git remote add origin <REMOTE_URL>

# To re-check your remote link, use this command
git remote -v
```

---

After everything are set up, let's synchronize our local repo with the remote one.

```bash
# Pushing a new branch require the '-u' arguments
git push -u origin <BRANCH_NAME>
```

You can check your GitHub repo to see if everything goes well

---

## Git Branch

---

A new branch is usually created when we need to have a new *development line*. For example, we want to add a new feature to a project, and require a *clean* workspace

![center height:350px](./assets/git_branch_illustration.png)

---

### Creating and switching to another Git branch

```bash
# Switch branch with git checkout
git checkout <BRANCH_NAME>

# Create a new branch and switch to it
git checkout -b <BRANCH_NAME>
```

---

## Merging Branch

---

In collaborative programming, usually you want to merge your newly created feature or fix to the main branch. To do this, you can use `git merge`

```bash
# Switch to the branch that you want
git checkout <BRANCH_NAME>

# Merge with the branch that you want to merge with current branch
git merge <MERGED_BRANCH_NAME>
```
