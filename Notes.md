# Learnings

## Git

### Rebase

`git pull -r`
When ever we have changes in the remote repo and our local repo, we cannot push our code cause our local and remote code doesn't match so we will have to pull the remote code and then we have to push our commits. while we do `git pull` first the remote code will be fetched and merged, then on `git push` our commits will be reflected in the remote repo but with two commits which doesnt look clean. `git pull -r` will make the push commits look clean by putting our recent commits on top.

### Stash

`git stash`
when ever we are working on one branch and we have made few code changes in any files and when we have to move to another branch then we cannot move cause we have few uncommittesd changes in the current branch. But we dont want to commit the changes cause the code isn't yest fininshed or something else but we want to move to another branch then we can TEMPORARLY save thosse changes and again on doing `git stash pop` in the stashed branch those changes will be visible.

#### Trick: when ever we made any changes and the app starts behaving unsual then we can stash our changes to check if the behaviour is because of our changes or not.

### History

`git log` to check all the commits made and we can even go back to the previous version and check by `git checkout 'hashcode'`

### Deleting

`git reset --Hard HEAD~1` this will reset, i mean this will revese the code changes and will also deletes the commit.
`git reset --soft HEAD~1` / `git reset HEAD~1` this will also reset but doest delete the commit instead it will pushes he previous code changes to staging area. we can then go and make changes to the code and we can comit it again later.
`git push --force` this force pushes you code to remote if you have made changes in the code and you have pushed the code to remote repo and now deleted tht commit in the local and watch to update the remote then you can force push, this will resolve the issue but not suggestable.

Instead you can revert the changes `git revert 'hashcode of commit'` this will add one more commit to the remote repo reversing all the changes we made in the previous commit.

### Merge

Lets say you are working on a branch which is far from few commit with the master branch, then first we have to `git pull` in the master branch from local then we have to move to the current working branch then we have to do `git merge` this will merge with the master branch locally then we have to push the code to remote repo. And then we can Raise merge request.
