# Git_Tutorial
Instructions of Git command. If something is useful or you find some mistakes, please let me know :)
If you have free time. I highly recommend watching the [Udacity: Version control](https://classroom.udacity.com/courses/ud123). Otherwise here is some basic command you may use in version control.

## What is Git?
> Git is a free and open source distributed version control system designed to handle everything from small to extensive projects with speed and efficiency. 

Download Git: [https://git-scm.com/downloads](https://git-scm.com/downloads)

## Why use Git?
1. Centralized cloud storage of your code
2. Backup your every milestone
3. Working with others
4. Organize your documents
5. ...

## Terminology
### Version Control System
The version control system (VCS) also called Source code manager(SCM) is a tool that manages different versions of source code.

### Commit
Commit like a checkpoint in games. You can rename it and go back to this checkpoint at any time.

### Repository / repo
A repository is a directory which contains your project work. The repository can exist either locally on your computer or as a remote copy on another computer. A repository is made up of commits.

### Working Directory
The Working Directory is the files that you see in your computer's file system. When you open your project files up on a code editor, you're working with data in the Working Directory.

### Checkout
A checkout is when content in the repository has been copied to the Working Directory.

### Staging Area / Staging Index / Index
A file in the Git directory that stores information about what will go into your next commit. You can think of the staging area as a prep table where Git will take the next commit. Files on the Staging Index are poised to be added to the repository.

### SHA
A SHA is basically an ID number for each commit. Here's what a commit's SHA might look like: `e2adf8ae3e2e4ed40add75cc44cf9d0a869afeb6`

### Branch
Every developer can create their branch that diverges from the main line of development. Each branch can modify without change the main branch.

## Git Init
Open your terminal and change the path to what you want. 
Run `git init` will generate all of the necessary files and directories that Git will use to keep track of everything.

## Git Clone
`git clone URL` you can use this command to clone project that you want. URL you can find on Github right top "Download or Clone."

## Git Status
The `git status` is our key to the mind of Git. It will tell us what Git is thinking and the state of our repository as Git sees it.
There is an example to show the information of `git status`:
```
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```
1. `On branch master` tells us that git is on the `master` branch
2. `Your branch is up-to-date with 'origin/master` this means our repository is the latest version
3. `nothing to commit, working directory clean` there are no pending changes

## Git Log
The `git log` shows all the details of our repository. Commit SHA, Author, Date and modified details.
`git log --oneline` shows the main information of each commit.
`git log -p` shows information per page.
`git log --stat` lists how many lines have been modified and where.
`git log 8d3ea36` you can watch the specific SHA.

## Git Add
While you update your file, you should `git add file-name` first. This command will put your file from the working directory into staging index. You can check status by `git status` every time. `git add .` The period `.` puts all files and directories to the staging index.

## Git Commit
`git commit` puts the file which is the staging index into the repository. Then you updated your file. As mentioned, you need to explain what you have done in this commit. `git commit -m 'explain what you have done in concision'`.
`git commit --amend` can alter the most-recent commit.

## Git Diff
The `git diff` command can be used to see changes that have been made but haven't been committed, yet.

## Git Ignore
If you have some files or docs, do not want to commit. You can use `touch .gitignore` to create a `.gitignore` file. Open this file while using your editor like `atom .gitignore`. Type the file name which you want to be ignored like `project.docx` and save `.gitignore`.

## Git Tag
Sometime we may have tons of commits, and we do not know which commits have great progress. We can use `git tag -a v1.0` to tag this progress.
`git tag -d v1.0` can delete 'v1.0' tag.

## Git Branch
The `git branch` can list all branch names in the repository, create new branches `git branch sidebar` or delete branch `git branch -d sidebar`. When we create a new branch, we can use `git checkout sidebar` to switch to `sidebar` branch. 
`git checkout -b new-branch` can create a new branch named `new-branch` and switch to it all in one command.

## Git Merge
The `git merge` can merge current branch repository with other repositories. `git merge sidebar`.
Some time merge may conflict, below are explanations:
- `<<<<<<< HEAD` everything below this line (until the next indicator) shows you what's on the current branch
- `||||||| merged common ancestors` everything below this line (until the next indicator) shows you what the original lines were
- `=======` is the end of the original lines, everything that follows (until the next indicator) is what's on the branch that's being merged in
- `>>>>>>> heading-update` is the ending indicator of what's on the branch that's being merged in (in this case, the `heading-update` branch)

## Git Revert
`git revert` will undo the changes that were made by the provided commit and created a new commit to record the change.

## Git Reset
`git reset` can be used to move the HEAD and current branch pointer to the referenced commit, erase commits(`git reset --hard`), move committed changes to the staging index(`git reset --soft`) and unstage committed changes(`git reset --mixed`).

## Parent Commit
- `HEAD^` `HEAD~` `HEAD~1` indicate the parent commit of the current commit
- `HEAD^^` `HEAD~2` indicate the grandparent commit of the current commit
- `HEAD^^^` `HEAD~3` indicate the great-grandparent commit of the current commit
The main difference between the `^` and the `~` is when a commit is created from a merge. A merge commit has two parents. With a merge commit, the `^` reference is used to indicate the first parent of the commit while `^2` indicates the second parent. The first parent is the branch you were on when you ran git merge while the second parent is the branch that was merged in.
