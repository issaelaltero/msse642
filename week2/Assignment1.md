# WEEK 1 ASSIGNMENT

ChatGPT results:

### What type is Git?

Git is a distributed version control system (DVCS). 
Each developer has a full copy of the repository, including the entire history.
Git tracks content as snapshots of the entire project directory.
(Chacon & Straub, 2014)

### Snapshots?

In Git, a snapshot is the saved state of all files at a specific time.
Git creates a new snapshot with each commit. If a file hasn't changed, 
Git links to the old file instead of copying it again.
(Chacon & Straub, 2014)

### What is a repository? Remote vs. local.

A repository (repo) stores your project's files and version history.
- Local repository: Located on your computer. Includes working directory, 
  staging area, and Git history (.git folder).
- Remote repository: Hosted on a server (like GitHub or GitLab). 
  Used for sharing and collaboration.
(Loeliger & McCullough, 2012)

### What is commit?

A commit is a saved snapshot of files in the staging area.
Each commit records what changed, who made the change, and when.
Commits have a unique SHA-1 hash and form the project's history.
(Chacon & Straub, 2014)

### What is working directory?

The working directory is where you actively edit files.
It reflects the current state of the project based on the last checkout.
Files here are not tracked unless staged.
(Loeliger & McCullough, 2012)

### What is Staging Area?

The staging area (or index) is where Git stores changes before a commit.
You use 'git add' to move changes to the staging area.
Only staged changes will be included in the next commit.
(Chacon & Straub, 2014)

### Diagram: Git Architecture and Flow

[Working Directory] --git add--> [Staging Area] --git commit--> [Local Repository]
                                                  |
                                                  |--git push--> [Remote Repository]

To update local:
[Remote Repository] --git pull--> [Local Repository] --checkout--> [Working Directory]

For visual diagram:
Git SCM. (n.d.). Git Basics - Getting a Git Repository.
https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository

### References:

Chacon, S., & Straub, B. (2014). *Pro Git* (2nd ed.). Apress. https://git-scm.com/book/en/v2

Loeliger, J., & McCullough, M. (2012). *Version Control with Git* (2nd ed.). O’Reilly Media.