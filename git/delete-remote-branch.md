# Delete remote branch

To delete a remote branch:
```sh
# you can do...
git push <remote_repo> :<branch_name>  

# ...or you can do...
git push <remote_repo> --delete <branch_name>
```

**example**:
This `til` project's `remote_repo` is named `origin` i.e. after executing `git remote -v` I get
```sh
origin	git@github.com:jbfrrr/til.git (fetch)
origin	git@github.com:jbfrrr/til.git (push)
```
To delete a branch, say `test` I can just do `git push origin :test` or `git push origin --delete test`.

**context**: I remembered (re-learned) this today because I inadvertently pushed a branch in one of our projects at work. The original intention was to merge it straight up.