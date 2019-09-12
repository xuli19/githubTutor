##github tutor
### show a system operation about how to use github for working
---
- step1: mkdir github_tutor 
> """create a directory for github repository"""
- step2:git init
> """initialize the directory,will generate a<.git>file"""
- step3:git branch  
> """list the current all branch"""
- step4:git branch test_github
> """create a new branch named test_github"""
- step5:git checkout test_github
> """change branch from master to test_github"""
- step6: do some changes(create file,modify contents,etc...)
- step7:git add .
- step8:git commit -m "commit messages"
- step9:git push --setup-stream  origin test_github
> ”“”push the new branch to remote repository"""
- step10：git checkout master
> """back to master branch"""
- step11:  git merge test_github
> """merge test_github to the current branch(master)"""
- step12: git branch -d test_github
> """delete the new branch located the current computer"""
- step13: git push
> """push the newest master to remote"""
- step14:git push origin :test_github
> """delete the remote branch named test_github


### if the remote repository has been modified, the local master has not been changed, how shoud i do for the next operation(modify the local file,then push to the remote)
---
- step1: git fetch origin/master 
> “”“this will get the remote origin/master branch to the local,but you will not see the obvious changes,because you need continue the step2."""
- step2: git merge master origin/master
> """the step will merge master and origin/master to master. then you will see the same content of master branch between local and remote."""

### if you want to rollback to last change or more elderly version, there will be a good example
---
- step1: git reflog  or  git log
> reflog will show all commit history with concise style, and log will show more information about commit history
> the first column is the id of every version
```git
8dbf72d (HEAD -> master, origin/master, origin/HEAD) HEAD@{0}: commit: fix some error.
5ffbda0 HEAD@{1}: commit: update the style of content
2a26626 HEAD@{2}: commit: add some content about how to merge the local branch and the remote branch if they have conflict on content.
9aba5d3 HEAD@{3}: merge origin/master: Merge made by the 'recursive' strategy.
602800d HEAD@{4}: commit: modify the tutor.md
8bc2a37 HEAD@{5}: merge test_delete: Fast-forward
c55683d HEAD@{6}: checkout: moving from test_delete to master
8bc2a37 HEAD@{7}: commit: delete branch
c55683d HEAD@{8}: checkout: moving from master to test_delete
c55683d HEAD@{9}: merge tutor_branch: Fast-forward
f4e2716 HEAD@{10}: checkout: moving from tutor_branch to master
c55683d HEAD@{11}: commit: create new branch
f4e2716 HEAD@{12}: checkout: moving from master to tutor_branch
f4e2716 HEAD@{13}: commit: add a file
a57ff04 HEAD@{14}: clone: from https://github.com/stephenlee4413/githubTutor.git
```
- step2: git reset --hard 602800d
