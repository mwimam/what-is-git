# Git Reference, branch, commits
## Git reference
3 type of git reference:
1. Tags & Annotated tags
- Tags are just a simple pointer to a commit. When you create a tag with no arguments, it captures the value in HEAD
- Annotated tags is point to a commit, but store additional information containing author, message, and date.
2. Branches
- Branch is pointer to a particular commit. pointer of current change when new commit are made
3. HEAD
- Head is active branch (or can be pointed to commit) you are working on.

### Tags vs Branch
- Tags pointed to commit and never change, but branch pointed to new commit (always change to new commit)
- 1 commit can have multiple tags
  
link : **[sample-branch-tags.txt](https://github.com/mwimam/what-is-git/blob/main/git-ref-merge-history/sample-branch-tags.txt)**

# Git Merge & Rebasing
Git merge are used for merge multiple parent commit. 2 common method to merge, fast-forward & No fast-forward
1. fast-forward
- Git has to do to integrate the histories is move the current branch tip up to the target branch tip. This will combines the histories, since all of the commits reachable from the target branch are now available through the current one
2. No fast-forward
- merge commit with retain history of commits

merge ilustrator : **[here](https://www.atlassian.com/git/tutorials/using-branches/git-merge)**  
there is also many marge strategy that can be used. example **[here](https://www.atlassian.com/git/tutorials/using-branches/merge-strategy)**

## Git Rerere (Reuse Recorded Resolution)
Is tool for conflicted merges. this tool is a really, really helpful tool. In a workflow employing relatively long lived topic branches, the developer sometimes needs to resolve the same conflicts over and over again until the topic branches are done (either merged to the "release" branch, or sent out and accepted upstream).
for more information can be read in **[here](https://git-scm.com/docs/git-rerere)**

# Git History & Diff
## Commit message 
commit message must describe the changes that occurred. good commit message will help for
1. Debugging & troubleshooting creating release notes
2. Code reviews
3. Rolling back
4. Associating the code with an issue or ticket
   
Details for each point and good commit message examples can be found on **[https://wiki.openstack.org/wiki/GitCommitMessages#Information_in_commit_messages](https://wiki.openstack.org/wiki/GitCommitMessages#Information_in_commit_messages)**

## Git Logs
Git log is command to show history of repository
```
git log 
```

## Git diff
Git diff is command to show different / changes between the working area and staging area
```
git diff 
```

## Git Show
Git show is used to view the details of a commit. It will display information about the file and the contents that were changed on a commit.
```
git show
```

## Git status
Git status is used to check changes between working area and stagging area
```
git status
```

use git "command" --help (without quotes) to see details about command