# Table Of Content
|                                                                                     	|                                                                                                                                                             	|                                                                                                                         	|
|-------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------	|
| **[What is git?](https://github.com/mwimam/what-is-git#what-is-git)**               	| **[Git Reference, branch, commits](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-reference-branch-commits)**                    	| **[Git Rebase, Abort, Amend](https://github.com/mwimam/what-is-git/tree/main/git-rebase-amend#git-rebase-abort-amend)** 	|
| **[Stored Data Git](https://github.com/mwimam/what-is-git#stored-data-git)**        	| **[Git Merge & Rebasing](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-merge--rebasing)**                                       	|                                                                                                                         	|
| **[Git Commits](https://github.com/mwimam/what-is-git#git-commits)**                	| **[Git History & Diff](https://github.com/mwimam/what-is-git/tree/main/git-ref-merge-history#git-history--diff)**                                           	|                                                                                                                         	|
| **[Git Area & Stashing](https://github.com/mwimam/what-is-git#git-area--stashing)** 	| **[Git Checkout, Reset, Revert & Clean](https://github.com/mwimam/what-is-git/tree/main/git-checkout-reset-revert-clean#git-checkout-reset-revert--clean)** 	|                                                                                                                         	|

# Git Rebase, Abort, Amend
## Rebase
move or give commit a new parent

<img width="300" alt="rebase vs merge" src="https://user-images.githubusercontent.com/85268979/149866491-09bc8860-d351-4736-b5ee-e8cb1169981a.png">


with rebase commit can be edited, removed, combined, re-ordered, inserted before they "replayed" on top of new HEAD

```
git rebase -i commit_to_fix^ -> the ^ specifict parent commit
```

rebase option
1. pick
- keep this commit
2. reword
- keep the commit, just change message
3. edit
- keep the commit, but stop edit more than message
4. squash
- combine this commit with the previous one, stop edit message
5. fixup
- combine this commit with the previous one, keep previous commit message
6. exec
- run the command on this line after picking the previous commit
7. drop
- remove the commit

### use rebase to split commits
1. start interactive rebase ``` git rebase -i ```
2. mark the commit with an edit
3. git reset HEAD^
4. git add
5. git commit
6. repeat (4) & (5) until working area clean
7. git rebase --continue

## Abort
git rebase abort is command for abort command when rebasing attempts are not working
```
git rebase --abort
```
## Amend
Amend is lets you to make changes to the previous commit

```
git commit --amend
```
