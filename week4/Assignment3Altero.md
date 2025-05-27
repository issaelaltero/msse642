# WEEK 4 ASSIGNMENT 3
ChatGPT results validated.

## Activity 1: Git CLI Questions

### Git Configurations:

1.a. What are the commands to configure your user.name and your user.email?

Globally (applies to all Git repositories):

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Locally (only for the current Git repository):

```
git config user.name "Your Name"
git config user.email "you@example.com"
```
1.b. Should this be configured globally or in your repo. Why or why not?

Globally: Ideal if you use the same identity across all projects.

Locally: Necessary if you use different identities (e.g., work vs personal email) for different projects.

Best practice: Use global config for common settings and local overrides for exceptions.

2. How do you configure the core editor for git?

To set your preferred text editor (e.g., Vim, VS Code):

```
git config --global core.editor "code --wait"        # VS Code
git config --global core.editor "vim"                # Vim
```

3. How do you view your global config and your local (for the repo) config.

Global config:

```
git config --global --list
```

Local (repo-specific) config:

```
git config --local --list
```

All config sources (system, global, local) in order of precedence:

```
git config --list --show-origin
```

### Working with a local repo:

4. What are the steps to create a new local repo via the CLI?

```
mkdir new-project
cd new-project
git init
```

5. How do you clone a repo and what's the difference between cloning and creating a new repo from scratch? Practice cloning a public repo from somewhere.

```
git clone https://github.com/granierregis/msse642-2025summer.git
```
This:
a. Downloads the repo (code, history, branches)
b. Sets up a local copy linked to the remote (usually origin)

Difference between cloning and creating:

| Creating a new repo  | Cloning an existing repo      |
| -------------------- | ----------------------------- |
| Starts empty         | Has existing files/history    |
| `git init`           | `git clone <url>`             |
| No remote by default | Automatically links to remote |

6. How do you look at the status of your repo? What information does this give you?

```
git status
```

Gives you:
a. The current branch name
b. Staged files (ready to be committed)
c. Unstaged changes (modified but not added)
d. Untracked files (new files not added to Git)
e. If the branch is ahead/behind the remote

7. How do you stage changes to your local repo in prepartion for a commit?

```
git add <filename> (stages a single file)
git add . (stages all changed files)
```

8. How do you commit changes to your local repo?

```
git commit -m "Your commit message"
```

9. Include an example of a file that will allow you to "ignore" files in your repo. What kinds of files should not be part of your version control?

.gitignore example file:

```
# Ignore system files
.DS_Store
Thumbs.db

# Ignore log files and environment variables
*.log
.env

# Ignore Python cache
__pycache__/
*.pyc

# Ignore build or distribution folders
/build/
/dist/

# Ignore IDE/editor configs
.vscode/
.idea/
```
Files to ignore:
a. OS-generated files.
b. Secret keys or environment files.
c. Logs and cache files.
d. Compiled files and build artifacts.
e. IDE/editor config folders.

10. When files are under version control, you can't delete them using the OS commands. How do you delete files using git.

```
git rm <filename>
git commit -m "Delete <filename>"
```

### Working with a remote:

11. How do you view the remote repo that is associated with your local repo?

```
git remote -v
```

This shows the remote names (e.g., origin) and their URLs (fetch and push).

12. What is the function of the git fetch command?

```
git fetch
```

This contacts the remote repository and downloads updates (commits, branches) but does NOT merge them into your local branch. It keeps your local code unchanged.

13. What is the difference between fetch and pull. Practice using both and show the results.

```
git fetch
```

a. Gets latest changes from the remote but does NOT apply them.

```
git pull 
```

 a. Gets and immediately merges changes into your current branch.
 b. This fetches and merges:
    i. The remote commits are now integrated into your working branch.
    ii. You may see automatic merge messages or conflicts depending on changes.


14. Make some changes in your repo and using the command line to sync those changes with your remote repo. Show the results.

Steps:

a. Make changes to a file (example: edit README.md)

b. Stage the changes:

```
git add README.md
```

c. Commit the changes:

```
git commit -m "Update README with project description"
```

d. Push the changes to the remote:

```
git push origin main
```

### Branches:

15. How do you view the local and the remote branches for your repositories?

View local branches:

```
git branch
```

View remote branches:

```
git branch -r
```

View all branches (local and remote):

```
git branch -a
```

16. View the local branches and create a new branch. Look again. Show before and after.

Before:

```
git branch
```

Example output:

```
* main
```

After: Create a new branch

```
git branch new-feature
```

Example output:

```
* main
  new-feature
```

17. What are different ways to switch to a new branch?

Method 1 - If the branch already exists:

```
git checkout new-feature
```

Method 2 - If you want to create and switch in one step (recommended):

```
git checkout -b new-feature
```

OR using the newer git switch command:

Method 3 - Switch to an existing branch:

```
git switch new-feature
```

Method 4 - Create and switch to a new branch:

```
git switch -c new-feature
```

18. Delete your local branch without pushing to a remote or merging to your main branch. Show that it's gone.

Example output before deletion:

```
* main
  new-feature
```

Delete the local branch:

```
git branch -d new-feature
```

Example output after deletion:

```
* main
```

