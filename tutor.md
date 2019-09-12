##github tutor
### show a system operation about how to use github for working
step1: mkdir github_tutor 
"""create a directory for github repository"""
step2:git init
"""initialize the directory,will generate a<.git>file"""
step3:git branch  
"""list the current all branch"""
step4:git branch test_github
"""create a new branch named test_github"""
step5:git checkout test_github
"""change branch from master to test_github"""
step6: do some changes(create file,modify contents,etc...)
step7:git add .
step8:git commit -m "commit messages"
step9:git push --setup-stream  origin test_github
”“”push the new branch to remote repository"""
step10：git checkout master
"""back to master branch"""
step11:  git merge test_github
"""merge test_github to the current branch(master)"""
step12: git branch -d test_github
"""delete the new branch located the current computer"""
step13: git push
"""push the newest master to remote"""
step14:git branch origin :test_github
"""delete the remote branch named test_github


### if the remote repository has been modified, the local master has not been changed, how shoud i do for the next operation(modify the local file,then push to the remote)
step1: git fetch origin/master 
“”“this will get the remote origin/master branch to the local,but you will not see the obvious changes,because you need continue the step2."""
step2: git merge master origin/master
"""the step will merge master and origin/master to master. then you will see the same content of master branch between local and remote."""

