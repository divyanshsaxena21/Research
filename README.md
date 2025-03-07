# Research


### Make your own branch and put your material in it, so that others can access it and refer.

## Git commands
```bash 
Important note before using push command 
Please use 
git pull origin <branch-name>
```
```bash
Make sure your local branch name must be same as the branch name in your github in which you are pushing 

to check branch name in your local machine 
1) open terminal(cmd,powershell,vscode terminal,etc)
git branch
the above command shows your branch name 
```
Here are some of the basic Git commands you'll need for version control:

### *Setup and Configuration*
1. *Configure Git (first-time setup)*
   - git config --global user.name "Your Name"
   - git config --global user.email "youremail@example.com"
   
2. *Check Git configuration*
   - git config --list

### *Creating and Cloning Repositories*
1. *Create a new Git repository*
   - git init

2. *Clone an existing repository*
   - git clone <repository-url>

### *Staging and Committing Changes*
1. *Check the status of your repository*
   - git status

2. *Stage changes for commit*
   - git add <file> (stage a single file)
   - git add . (stage all changes)

3. *Commit changes*
   - git commit -m "Your commit message"

### *Viewing Changes*
1. *View changes before staging*
   - git diff

2. *View changes between commits*
   - git diff <commit1> <commit2>

3. *View the commit history*
   - git log

4. *View a simplified log (one-line format)*
   - git log --oneline

### *Branching and Merging*
1. *Create a new branch*
   - git branch <branch-name>

2. *List all branches*
   - git branch

3. *Switch to a branch*
   - git checkout <branch-name>

4. *Create a new branch and switch to it*
   - git checkout -b <branch-name>

5. *Merge a branch into the current branch*
   - git merge <branch-name>

6. *Delete a branch*
   - git branch -d <branch-name> (local branch)
   - git branch -D <branch-name> (force delete)

### *Remote Repositories*
1. *Add a remote repository*
   - git remote add origin <repository-url>

2. *View remote repositories*
   - git remote -v

3. *Push changes to a remote repository*
   - git push origin <branch-name>

4. *Pull changes from a remote repository*
   - git pull origin <branch-name>

5. *Fetch changes from a remote repository without merging*
   - git fetch

6. *Remove a remote repository*
   - git remote remove <remote-name>

### *Undoing Changes*
1. *Unstage a file*
   - git reset <file>

2. *Unstage all files*
   - git reset

3. *Discard local changes (in a file)*
   - git checkout -- <file>

4. *Reset the repository to a previous commit (hard reset)*
   - git reset --hard <commit-id>

### *Other Useful Commands*
1. *Show the difference between staged and unstaged changes*
   - git diff --staged

2. *View details of a specific commit*
   - git show <commit-id>

3. *Revert a commit (create a new commit to undo changes)*
   - git revert <commit-id>

4. *Tag a commit (for release or milestone purposes)*
   - git tag <tag-name>

5. *Push tags to the remote repository*
   - git push origin <tag-name>

These are just some of the most basic and commonly used Git commands to get you started with version control!
