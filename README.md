# Git_Tutorial🤩
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

`git shortlog`, a quick way that we can see how many commits each contributor has added to the repository

⚠️`git shortlog -s -n` If we just want to see just the number of commits that each developer has made, we can add a couple of flags: `-s` to show just the number of commits (rather than each commit's message) and `-n` to sort them numerically (rather than alphabetically by author name). (By Udacity)

`git log --author=Surma` filter by author

How about we filter down to just the commits that reference the word "bug". We can do that with either of the following commands:
```
git log --grep=bug
git log --grep bug
```

**If the key words have space, you need to wrap everything in quotes.**
```
git log --grep="unit tests"
```

Grep is a pattern matching tool. It is way beyond the scope of this course to cover grep. But as a brief intro, if you were to run `git log --grep "fort"`, then Git will display only the commits that have the character `f` followed by the character `o` followed by `r` followed by `t`.

## Git Branch
The `git branch` can list all branch names in the repository, create new branches 
`git branch sidebar` or delete branch `git branch -d sidebar`. When we create a new branch, we can use `git checkout sidebar` to switch to `sidebar` branch. 
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

# GitHub Tutorial🤪

## Git Remote
The `git remote` is used to connect your local commited file to the online repository. 

You should `git init` your local file, and create 'README.md' file by command `touch README.md`. Then commit it.

After that, create a new repository on the GitHub that has the same name with your local file name.

⚠️**Notice! DO NOT initial README.md file on GitHub**⚠️

Then `git remote add nameyouwant URL(from the GitHub)`, the local file will connect with your online repository.

You also can use `git remot -v` to check whethere or not.

If shows like 
```
origin	https://github.com/ChenMetanoia/my-travel-plans.git (fetch)
origin	https://github.com/ChenMetanoia/my-travel-plans.git (push)
```
Then you success! 🙌

`git remote rename origin mine` can change remote name


## Git Push
`git push origin master` upload your local commited file to the GitHub and in `master` branch.

## Git Pull
If there are changes in a remote repository that you'd like to include in your local repository, then you want to pull in those changes. To do that with Git, you'd use the `git pull` command. You tell Git the shortname of the remote you want to get the changes from and then the branch that has the changes you want:
```
git pull origin master
```
When `git pull` is run, the following things happen:
- the commit(s) on the remote branch are copied to the local repository
- the local tracking branch (`origin/master`) is moved to point to the most recent commit
- the local tracking branch (`origin/master`) is merged into the local branch (`master`) -Udacity

## Git Fetch
`git fetch origin master` Git fetch is used to retrieve commits from a remote repository's branch but it does not automatically merge the local branch with the remote tracking branch after those commits have been received. (By Udacity)

You can think of `git fetch` as half of a `git pull`. The other half of `git pull` is the merging aspect. (By Udacity)

One main point when you want to use `git fetch` rather than `git pull` is if your remote branch and your local branch both have changes that neither of the other ones has. In this case, you want to fetch the remote changes to get them in your local branch and then perform a merge manually. Then you can push that new merge commit back to the remote. (By Udacity)

## Fork
It means "filesystem check" and refers to auditing the files for consistency. In version control terminology if you "fork" a repository that means you duplicate it. Typically you fork a repository that belongs to someone else. So you make an identical copy of their repository and that duplicate copy now belongs to you. (By Udacity)

This concept of "forking" is also different from "cloning". When you clone a repository, you get an identical copy of the repository. But cloning happens on your local machine and you clone a remote repository. When you fork a repository, a new duplicate copy of the remote repository is created. This new copy is also a remote repository, but it now belongs to you. (By Udacity)

If you need to keep up with a project's changes and want to be notified of when things change, GitHub offers a "Watch" feature. After "Watch", command `git remote add upstream URL` gives a connection to the source repository. When the source repository has update, we can use `git fetch upstream master` to update the new version to our local repository. So cooooooooool! 🥳

## Git Rebase
> `git rebase`
> Let's look different commands that you can do with `git rebase`:
> - use `p` or `pick` – to keep the commit as is
> - use `r` or `reword` – to keep the commit's content but alter the commit message
> - use `e` or `edit` – to keep the commit's content but stop before committing so that you can:
>   - add new content or files
>   - remove content or files
>   - alter the content that was going to be committed
> - use `s` or `squash` – to combine this commit's changes into the previous commit (the commit above it in the list)
> - use `f` or `fixup` – to combine this commit's change into the previous one but drop the commit message
> - use `x` or `exec` – to run a shell command
> - use `d` or `drop` – to delete the commit

### When to rebase
>
> As you've seen, the `git rebase` command is incredibly powerful. It can help you edit commit messages, reorder commits, combine commits, > > etc. So it truly is a powerhouse of a tool. Now the question becomes "When should you rebase?".
>
> Whenever you rebase commits, Git will create a new SHA for each commit! This has drastic implications. To Git, the SHA is the identifier > for a commit, so a different identifier means it's a different commit, regardless if the content has changed at all.
>
> So you should not rebase if you have already pushed the commits you want to rebase. If you're collaborating with other developers, then > they might already be working with the commits you've pushed. If you then use `git rebase` to change things around and then force push the > commits, then the other developers will now be out of sync with the remote repository. They will have to do some complicated surgery to > their Git repository to get their repo back in a working state...and it might not even be possible for them to do that; they might just > have to scrap all of their work and start over with your newly-rebased, force-pushed commits.
