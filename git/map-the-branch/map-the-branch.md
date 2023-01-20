Check for the existence of a branch mapping, the following warning will appear if the mapping does not exist.

```
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull (1) for details.
git pull <remote> <branch>
If you wish to set tracking information 
for this branch you can do so with:
git branch --set-upstream-to = origin / <branch> branchname
 ```

Checkout the branch where you want to create the mapping.
``` bash
git checkout branchname
```

Tell the upstream which branch is mapping.
``` bash
git branch --set-upstream-to=origin/branchname branchname
```

From now on, instead of always informing the origin such as: git pull origin master, you will only request: git pull, as the branch is already mapped
