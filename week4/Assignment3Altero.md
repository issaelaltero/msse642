# WEEK 4 ASSIGNMENT 3

## Activity 1: Git Hub Command Line

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

Use --global to apply it system-wide, or omit it to configure only for the current repo.

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

### Working with a remote:

### Branches
