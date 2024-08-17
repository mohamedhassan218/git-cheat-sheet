# Git Cheat Sheet
<a name="top"></a>


## Introduction

This repo is designed to serve as a comprehensive and easy-to-reference guide for all levels of Git users. Whether you're a beginner just getting started with version control or an experienced developer looking to refine your workflow, this cheat sheet covers a wide range of commands and techniques to help you work more efficiently with Git.


## **Basic Commands**
- Initialize a new Git repository in the current directory.
    ```bash
        git init
    ```

- Clones a repository into a new directory.
    ```bash
        git clone <repository>
    ```

- Shows the working directory status.
    ```bash
        git status
    ```

- Stages a file for the next commit.                    
    ```bash
        git add <file>
    ```

- Stages all files (new, modified, deleted) in the current directory.
    ```bash
        git add .
    ```
  
- Commits the staged changes with a message.
    ```bash
        git commit -m "message"
    ```

- Stages and commits all modified files (skipping new files).
    ```bash
        git commit -am "message"
    ```

- Shows the commit history.
    ```bash
        git log
    ```


## **Branching & Merging**
- Lists all branches.
    ```bash
        git branch
    ```
- Creates a new branch.
    ```bash
        git branch <branch-name>
    ```
  
- Switches to the specified branch.
    ```bash
        git checkout <branch-name>
    ```

- Creates a new branch and switches to it.
    ```bash
        git checkout -b <branch-name>
    ```  

- Merges the specified branch into the current branch.
    ```bash
        git merge <branch-name>
    ```

- Deletes the specified branch.  
    ```bash
        git branch -d <branch-name>
    ```


## **Remote Repositories**
- Shows the remote repositories.
    ```bash
        git remote -v
    ```

- Adds a new remote repository.
    ```bash
        git remote add <name> <url>
    ```

- Pushes changes to the specified remote branch.
    ```bash
        git push <remote> <branch>
    ```

- Pushes changes and sets the upstream branch for the current branch.
    ```bash
        git push -u <remote> <branch>
    ```

- Fetches and merges changes from the specified remote branch.
    ```bash
        git pull <remote> <branch>
    ```

- Fetches changes from the remote but doesn’t merge them.
    ```bash
        git fetch <remote>
    ```


## **Stashing**
- Temporarily saves changes for later.
    ```bash
        git stash
    ```

- Applies the stashed changes and removes them from the stash list.
    ```bash
        git stash pop
    ```

- Applies the stashed changes without removing them from the stash list.
    ```bash
        git stash apply
    ```

- Lists all stashed changes.
    ```bash
        git stash list
    ```

- Deletes a specific stash from the stash list.
    ```bash
        git stash drop
    ```


## **Undoing Changes**
- Unstages a file without discarding changes.
    ```bash
        git reset <file>
    ```

- Resets the working directory to the last commit (all changes will be lost).
    ```bash
        git reset --hard
    ```

- Moves the HEAD back by one commit, keeping changes in the staging area.
    ```bash
        git reset --soft HEAD~1
    ```

- Creates a new commit that undoes the changes from the specified commit.
    ```bash
        git revert <commit>
    ```


## **Tagging**
- Creates a new tag at the current commit.
    ```bash
        git tag <tag-name>
    ```

- Creates an annotated tag.
    ```bash
        git tag -a <tag-name> -m "message"
    ```

- Pushes the tag to the remote repository.
    ```bash
        git push origin <tag-name>
    ```

## **Viewing Differences**
- Shows the differences between the working directory and the staging area.
    ```bash
        git diff
    ```

- Shows the differences between the staging area and the last commit.
    ```bash
        git diff --staged
    ```


## **Configuration**
- Sets your Git username.
    ```bash
        git config --global user.name "Your Name"
    ```

- Sets your Git email.
    ```bash
        git config --global user.email "you@example.com"
    ```

- Lists all Git configurations.
    ```bash
        git config --list
    ```


## **Advanced Branching**
- Creates a new branch from a remote branch and sets up tracking.
    ```bash
        git checkout --track origin/<branch-name>
    ```

- Renames the current branch.
    ```bash
        git branch -m <new-branch-name>
    ```

- Renames a specified branch.
    ```bash
        git branch -m <old-branch-name> <new-branch-name>
    ```

- Lists remote branches.
    ```bash
        git branch -r
    ```

- Lists all branches (local and remote).
    ```bash
        git branch -a
    ```

- Deletes a remote branch.
    ```bash
        git push <remote> --delete <branch-name>
    ```


## **Rebasing**
- Reapplies commits on top of another base tip.
    ```bash
        git rebase <branch>
    ```

- Interactive rebase starting from a specific commit (useful for squashing commits).
    ```bash
        git rebase -i <commit>
    ```

- Aborts the rebase and returns to the state before rebase.
    ```bash
        git rebase --abort
    ```

- Continues the rebase after resolving conflicts.
    ```bash
        git rebase --continue
    ```


## **Cherry-Picking**
- Applies the changes from a specific commit to the current branch.
    ```bash
        git cherry-pick <commit>
    ```

- Aborts the cherry-pick process.
    ```bash
        git cherry-pick --abort
    ```


## **Resetting**
- Removes the most recent commit, keeping changes in the working directory.
    ```bash
        git reset HEAD~1
    ```

- Removes the most recent commit and discards changes.
    ```bash
        git reset --hard HEAD~1
    ```

- Resets the index but not the working directory (default reset type).
    ```bash
        git reset --mixed
    ```


## **Reverting**
- Reverts a commit without committing the changes (useful for batch reverts).
    ```bash
        git revert -n <commit>
    ```


## **Amending Commits**
- Edits the last commit (useful for changing the commit message or adding files).
    ```bash
        git commit --amend
    ```

- Amends the last commit without changing the commit message.
    ```bash
        git commit --amend --no-edit
    ```


## **Logging & History**
- Displays the commit history in a compact format (one line per commit).
    ```bash
        git log --oneline
    ```

- Shows a graphical representation of branches and commits.
    ```bash
        git log --graph --oneline --all
    ```

- Displays each commit’s changes (patches).
    ```bash
        git log -p
    ```

- Shows commit statistics (files changed, insertions, deletions).
    ```bash
        git log --stat
    ```

- Shows commits by a specific author.
    ```bash
        git log --author="<name>"
    ```

- Shows the commit history for a specific file.
    ```bash
        git log <file>
    ```


## **Diffing**
- Shows the differences between two branches.
    ```bash
        git diff <branch1> <branch2>
    ```

- Shows the differences between two commits.
    ```bash
        git diff <commit1> <commit2>
    ```

- Shows the differences for a specific file between a commit and the working directory.
    ```bash
        git diff <commit> <file>
    ```


## **Aliases**
- Creates an alias `git st` for `git status`.
    ```bash
        git config --global alias.st status
    ```

- Creates an alias `git co` for `git checkout`.
    ```bash
        git config --global alias.co checkout
    ```

- Creates an alias `git br` for `git branch`.
    ```bash
        git config --global alias.br branch
    ```

- Creates an alias `git cm` for `git commit`.
    ```bash
        git config --global alias.cm commit
    ```


## **Working with Submodules**
- Adds a submodule to your repository.
    ```bash
        git submodule add <repository>
    ```

- Clones submodules and initializes them.
    ```bash
        git submodule update --init --recursive
    ```

- Updates all submodules.
    ```bash
        git submodule foreach 'git pull origin master'
    ```

- Deinitializes a submodule.
    ```bash
        git submodule deinit <path>
    ```


## **Cleaning Up**
- Removes untracked files from the working directory.
    ```bash
        git clean -f
    ```

- Removes untracked files and directories.
    ```bash
        git clean -fd
    ```

- Removes ignored files.
    ```bash
        git clean -fx
    ```


## **Temporary Work**
- Creates a new working directory linked to a specific branch.
    ```bash
        git worktree add <path> <branch>
    ```

- Lists all active worktrees.
    ```bash
        git worktree list
    ```


## **Blaming**
- Shows who made the last change to each line of a file.
    ```bash
        git blame <file>
    ```

- Limits blame to lines 10 through 20.
    ```bash
        git blame <file> -L 10,20
    ```


## **Archiving**
- Creates a zip archive of a branch.
    ```bash
        git archive --format=zip --output=archive.zip <branch>
    ```


## **Working with Tags**
- Shows information about a tag.
    ```bash
        git show <tag-name>
    ```

- Deletes a local tag.
    ```bash
        git tag -d <tag-name>
    ```

- Deletes a remote tag.
    ```bash
        git push origin :refs/tags/<tag-name>
    ```


## **Rewriting History (Advanced)**
- Rewrites history to remove a file from all commits.
    ```bash
        git filter-branch --tree-filter 'rm -rf <file>' HEAD
    ```

- Allows you to squash, edit, or reword commits in an interactive rebase.
    ```bash
        git rebase -i <commit>
    ```

- Shows a log of all reference updates (useful for recovering lost commits).
    ```bash
        git reflog
    ```


## **Collaboration**
- Summarizes contributions per author.
    ```bash
        git shortlog -s -n
    ```

- Pushes all branches that match between local and remote.
    ```bash
        git config --global push.default matching
    ```

- Pushes only the current branch to its upstream branch.
    ```bash
        git config --global push.default simple
    ```


## **Git Hooks**
- Enables a sample pre-commit hook.
    ```bash
        cp pre-commit.sample pre-commit
    ```

- Executes Git hooks for additional checks (e.g., code formatting).
    ```bash
        git hook apply
    ```


## **Patching**
- Prepares patch files from commits.
    ```bash
        git format-patch <start-commit>
    ```

- Applies a patch file to your current branch.
    ```bash
        git apply <patch-file>
    ```


## **Remotes**
- Renames a remote.
    ```bash
        git remote rename <old> <new>
    ```

- Changes the URL of a remote.
    ```bash
        git remote set-url <name> <new-url>
    ```

- Updates all branches and tags from remotes.
    ```bash
        git remote update
    ```


## **Squashing Commits**
- Squashes the last `n` commits into one.
    ```bash
        git rebase -i HEAD~<n>
    ```

## **Working with Large Files**
- Initializes Git Large File Storage (LFS) in the repository.
    ```bash
        git lfs install
    ```

- Tracks files matching the specified pattern with LFS.
    ```bash
        git lfs track "<pattern>"
    ```

- Pushes all LFS-tracked files to the remote.
    ```bash
        git lfs push --all
    ```

