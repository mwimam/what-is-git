# Table Of Content
|                     	|                                     	|                          	|
|---------------------	|-------------------------------------	|--------------------------	|
| **[What is git?](https://github.com/mwimam/what-is-git#what-is-git)**        	| **[Git Reference, branch, commits](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-reference-branch-commits)**      	| **[Git Rebase, Abort, Amend](https://github.com/mwimam/what-is-git/tree/main/git-rebase-amend#git-rebase-abort-amend)** 	|
| **[Stored Data Git](https://github.com/mwimam/what-is-git#stored-data-git)**     	| **[Git Merge & Rebasing](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-merge--rebasing)**                	|                          	|
| **[Git Commits](https://github.com/mwimam/what-is-git#git-commits)**         	| **[Git History & Diff](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-history--diff)**                  	|                          	|
| **[Git Area & Stashing](https://github.com/mwimam/what-is-git#git-area--stashing)** 	| **[Git Checkout, Reset, Revert & Clean](https://github.com/mwimam/what-is-git/tree/main/git-checkout-reset-revert-clean#git-checkout-reset-revert--clean)** 	|                          	|

# What is git?
Git is is distributed version control system that store data in key - value. its means value is data and key is hash of data. we need key to retreive the content. The key are hashed with SHA-1 which produce 40-digit hexadecimal. Git will stored compressed data in BLOB with metadata in header:
 1. identifier BLOB
 2. size of content
 3. \0 as delimeter
 4. content

link : **[sample.stored-data-git.txt](https://github.com/mwimam/what-is-git/blob/main/sample.stored-data-git.txt)**
# Stored Data Git
Git stores project information and its metadata into blob, tree, and commits objects. its data on .git folder on your repository.
directory structure are :
```
├── FETCH_HEAD
├── HEAD
├── branches
├── config
├── description
├── hooks
├── index
├── info
├── logs
├── objects
├── packed-refs
└── refs
```

BLOB will be store on **objects** folder.
git store information in a tree. 
A tree thet contains pointer: 
1. to blob
2. another tree

and metadata:
1. type of pointer (blob or tree)
2. filename or directory name
3. mode (executable file, symbolic link, etc)

Deleting .git folder will delete information and history of the project, but not the files of the project.

# Git Commits
git commit is an object that stores the current contents of the project in a new commit with a log message from the user describing the changes.
commits contains:
1. tree

and metadata:
1. author and commiter
2. date
3. message
4. parent commit (one or more)

link : **[sample.commit-tree-git.txt](https://github.com/mwimam/what-is-git/blob/main/sample.commit-tree-git.txt)**

# Git Area & Stashing

## Git Area
3 Area that code live : 
1. Working Area, files that are not handled by git. its means your changes file or directory. These files are also referred to as "untracked files."
2. Staging area, is files that are going to be a part of the next commit, which lets git know what changes in the file are going to occur for the next commit.
3. The repository contains all of a project's commits.

![image](https://user-images.githubusercontent.com/85268979/149746340-7b63a4b1-6c43-457f-beee-881c6f9a8605.png)

link : **[sample-working-area.git.txt](https://github.com/mwimam/what-is-git/blob/main/sample-working-area.git.txt)**

## Git Stashing
Git stash which is saving work that is not committed to a git repo and is also safe from destructive operations.

Stash Apply vs stash pop
- stash Apply, stash will not remove after apply/move from stash list to working area
- stash Pop, stash will remove after apply/move from stash list to working area (if there's merge conflict, stash will not remove or deleted)

link : **[sample-stash-git.txt](https://github.com/mwimam/what-is-git/blob/main/sample-stash-git.txt)**

reference :
- **[frontendmaster](https://frontendmasters.com)**.
- **[git docs](https://git-scm.com/docs/git-log)**.
- **[git tutorial atlassian](https://www.atlassian.com/git/tutorials/using-branches/git-merge)**.
