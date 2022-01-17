# Table Of Content
|                                                                                     	|                                                                                                                                                             	|                                                                                                                         	|
|-------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------	|
| **[What is git?](https://github.com/mwimam/what-is-git#what-is-git)**               	| **[Git Reference, branch, commits](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-reference-branch-commits)**                    	| **[Git Rebase, Abort, Amend](https://github.com/mwimam/what-is-git/tree/main/git-rebase-amend#git-rebase-abort-amend)** 	|
| **[Stored Data Git](https://github.com/mwimam/what-is-git#stored-data-git)**        	| **[Git Merge & Rebasing](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-merge--rebasing)**                                       	|                                                                                                                         	|
| **[Git Commits](https://github.com/mwimam/what-is-git#git-commits)**                	| **[Git History & Diff](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-history--diff)**                                           	|                                                                                                                         	|
| **[Git Area & Stashing](https://github.com/mwimam/what-is-git#git-area--stashing)** 	| **[Git Checkout, Reset, Revert & Clean](https://github.com/mwimam/what-is-git/tree/main/git-checkout-reset-revert-clean#git-checkout-reset-revert--clean)** 	|                                                                                                                         	|

# Git Checkout, Reset, Revert & Clean
## Checkout
Restoring working tree files or switch to another branch
you can checkout to branch, file, or commit. when checkout to file or commit, working area will replace / overwrite with data from stagging area.
```
git checkout new_branch

git checkout -- file_path

git checkout commit -- file_path
```

## Reset 
git reset is a command that is used to undo local changes to the state of a Git repo
when reset to commit, it will move the HEAD pointer
when reset file path, doesn't move the HEAD pointer

default git reset use mixed operation (if operation didn't typed).
```
git reset --soft HEAD~ (reset to previous commit on repo)

git reset --mixed HEAD~ (reset to previous commit on repo, and stagging area reset to previous commit)

git reset --hard HEAD~ (reset to previous commit on repo , and stagging area & working area reset to previous commit)
```

## Clean
clean your working area by deleting untracked files, be careful becase this operation can't be undone

```
git clean

git clean --dry-run (flag to see what would be deleted)
```

## Revert
git revert is "safe" reset. git will create new commits from the specified commit. the original commit stays in the repository
revert doesn't change history. you can use revert if you're undoing commit that has been already shared

```
git revert (commit)
```