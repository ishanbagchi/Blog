# Git Cheatsheet (At a glance)

## Contents:
- [What is Git](#what-is-git)
- Git commands to:
    - [Prepare Repository](#git-commands-to-prepare-repository)
    - [Configuration](#git-commands-for-configuration)
    - [Work With Repository](#git-commands-to-work-with-repository)
    - [Manage Branch](#git-commands-to-manage-branch)
    - [Manage Tags](#git-commands-to-manage-tags)
    - [Stash Working Directory](#-git-commands-to-stash-working-directory)
    - [Remote Repository](#git-commands-to-remote-repository)
    - [Repository Maintenance](#git-commands-for-repository-maintenance)
- [Conclusion](#conclusion)

## What is Git?

Git is a free and open-source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

## Git commands to **Prepare Repository**:

> ## Initialise Repository
> `git init`\
> Create new empty repository in current directory

> ## Clone Repository
> `git clone <url> <dir>`\
> Clone repository from the _url_ named _dir_

### Move to [Contents](#contents)

## Git commands for **Configuration**:

> ## Show Configurations
> `git config --list`\
> Show current configurations

> ## Set User Name
> `git config user.name <"name">`\
> Set comitter username

> ## Set User Email
> `git config user.email <"email">`\
> Set commiter email address

> ## Unix/Windows EOL Conversion
> `git config core.autocrlf true`\
> Automatically convert between Unix and Windows end of the line on commit and checkout

> ## EOL Conversion on Save Only
> `git config core.autocrlf input`\
> Convert CRLF to LF only when committing, use original line ending on checkout

> ## Change Editor
> `git config core.editor <editor>`\
> Change text editor for writing commit message

> ## Get Configuration
> `git config --get <config-name>`\
> Get configuration value for the configuration name

> ## Unset Configuration
> `git config --unset <config-name>`\
> Unset configuration value for given configuration name

> ## Configuration Scope
> `git config [--global | --system] <name> <value>`\
> -- local or none for current repo, --global for user scope, --system for system scope

### Move to [Contents](#contents)

## Git commands to **Work With Repository**

> ## Show Status
> `git status`\
> Show working directory status, what files changed

> ## Add File to Index
> `git add <file>`\
> Add file or directory to the index for the next commit

> ## Add Modified Files
> `git add -u`\
> Update modified files to the index, it will not add new files

> ## Add All Files
> `git add -A`\
> Add all file or directory to the index for the next commit

> ## Remove File from Index
> `git restore --staged <file>`\
> Remove file from index, file on current directory unaffected

> ## Discard Modification
> `git checkout -- <file>`\
> Discard file modification, restore file from index

> ## Delete File
> `git rm <file>`\
> Delete file in the working directory and the index

> ## Commit Changes
> `git commit -m ["commit message"]`\
> Apply changes in the index with given commit message

> ## Reverse Commit
> `git commit --amend`\
> Replace the last commit of the current branch with the current index

> ## Reset Author
> `git commit --amend --reset-author`\
> Amend commit author and author-date to the committer

> ## Change Author
> `git commit --amend --author="Author Name <email>"`\
> Amend commit author with given author name and email, author date unchanged

> ## Change Author Date
> `git commit --amend --date="2020-11-21T23:59:59"`\
> Amend author date, use ISO 8601 format for convenience

> ## Show Commit Log
> `git log [-n <number>]`\
> Show commit logs, limit showing \<number\> commits

> ## Show Short Log
> `git shortlog`\
> Show shorter commit log

> ## Show Log Summary
> `git shortlog -s`\
> Show even shorter commit count summary

> ## Diff Working Directory and Branch
> `git diff <branch-name>`\
> Show diff between a branch and working directory

> ## Show Diff between Branches
> `git diff <branch-1> <branch-2>`\
> Show diff between two branches

### Move to [Contents](#contents)

## Git commands to **Manage Branch**

> ## Detach Branch
> `git checkout --detach`\
> Detach HEAD from current branch

> ## Create New Branch
> `git checkout -b <branch-name>`\
> Create new branch starting from current head

> ## Switch Branch
> `git checkout <branch-name>`\
> Change active branch

> ## Checkout to Commit-Name
> `git checkout <commit-name>`\
> Checkout to commit-name. Commit name can be branch name, commit hash, or relative HEAD reference

> ## Checkout to Previous Commit
> `git checkout <HEAD~1>`\
> Detach HEAD and switch to the previous commit. Where ~1 is the previous commit, ~2 is the previous 2 commits

> ## Reset Current Head
> `git reset --hard <commit-name>`\
> Move current branch HEAD to commit-name. Changes in index AND working directory are discarded. Potentially causing commits after a commit-name loss. USE WITH CAUTION

> ## List Branches
> `git branch [--list]`\
> List local branches

> ## List Remote Tracking Branches
> `git branch -r`\
> List remote-tracking branches

> ## List Branches and Commit Messages
> `git branch -v`\
> List branches, hash, and commit message

> ## Sort Branches by Committer Date
> `git branch -v --sort=commiterdate`\
> List branches, hash, and commit message sort by committer date

> ## Sort Branches by Author Date
> `git branch -v --sort=authordate`\
> List branches, hash and commit messages, sort by author-date

> ## List All Branches
> `git branch -a`\
> List both local and remote-tracking branches

> ## Delete Branch
> `git branch -d <branch-name>`\
> Delete already merged branch

> ## Force Delete Branch
> `git branch -D <branch-name>`\
> Delete branch, even unmerged. USE WITH CAUTION

> ## Merge Branch
> `git merge <other-branch>`\
> Merge other branches with current branch, fast-forward if possible

> ## Merge Using Merge Commit
> `git merge --no-ff <other-branch>`\
> Merge other branch, use merge commit

> ## Interactive Branch Rebase
> `git rebase -i <other-branch>`\
> Rebase current branch with other branch interactively

### Move to [Contents](#contents)

## Git commands to **Manage Tags**

> ## List Tags
> `git tag`\
> List available tags

> ## Add Tags
> `git tag <tag-name>`\
> Create new lightweight tag named \<tag-name\>

> ## Delete Tags
> `git tag -d <tag-name>`\
> Delete a tag named \<tag-name\>

### Move to [Contents](#contents)

## Git commands to **Stash Working Directory**

> ## Stash Working Directory
> `git stash save`\
> Save working directory state to new stash and clean up the working directory

> ## List Stashes
> `git stash list`\
> List stashes, stash@{0} is last stash

> ## Restore Stash
> `git stash pop`\
> Restore the last stash and apply it to the working directory

> ## Remove Last Stash
> `git stash drop`\
> Remove the last stash, saved state will be discarded

> ## Clear Stashes
> `git stash clear`\
> Remove all stashes, saved state will be discarded

### Move to [Contents](#contents)

## Git commands to **Remote Repository**

> ## Show Remote Repositories
> `git remote -v`\
> Show remote repositories name and URL for push fetch

> ## Add Remote Repository
> `git remote add <remote-name> <url>`\
> Add new remote repository with given remote name

> ## Push branch to remote
> `git push <remote-name> <branch-name>`\
> Push local branch to remote repository

> ## Delete Remote Branch
> `git push --delete <remote-name> <branch-name>`\
> Delete a branch from remote repository

> ## Push Tag
> `git push <remote-name> <tag-name>`\
> Push single local tag to remote repository

> ## Push All Tags
> `git push --tags <remote-name>`\
> Push all local tags to remote repository

> ## Delete Remote Tag
> `git push --delete <remote-name> <tag-name>`\
> Delete a tag from remote repository

> ## Fetch from Remote
> `git fetch <remote-name>`\
> Update remote-tracking branches. Remote tracking branches are NOT automatically merged with local branches. Use _git branch -r_ to list-remote tracking branches

> ## Pull from Remote
> `git pull <remote-name> <branch-name>`\
> Retreve objects from remote-branches, and merge with current branch. USE WITH CAUTION

### Move to [Contents](#contents)

## Git commands for **Repository Maintenance**

> ## Optimize Repository
> `git gc`\
> Remove unnecessary files and references, optimize repository. It is a good idea to run gc periodically

> ## Optimize Repository if Required
> `git gc --auto`\
> Check and run gc only if required, otherwise exit without doing gc

> ## Check Repository
> `git fsck`\
> Check integrity of objects in the repository

### Move to [Contents](#contents)

## Conclusion

I mentioned some of the most used git commands. To learn more about git commands, visit the official git documentation [here](https://git-scm.com/docs).