# Resolving conflicts with `ours` and `theirs`

While `git` is inherently good at resolving conflicts in our code when we've branched out from some master branch, there are times wherein it couldn't decide which one we want to follow from a certain point.

Luckily we don't have to do everything entirely manually all the time. `git` has commands such as `git checkout --ours <filename>` and `git checkout --theirs <filename>` which would automatically resolve conflicts by following the changes from a particular branch instead of the master or vice-versa if that's what we wanted.

**CAVEAT!** The context of `ours` and `theirs` could change depending on how we use it.

#### Usage 1: `rebase` conflict resolution
```sh
$ git co testbranch
$ git rebase master
# encouter conflict here...
```
In this situation, if you want to follow all changes for a file coming from `testbranch`, then we should do `git co --theirs <filename>`. This is because rebase replays all the commits from "our" current `testbranch` ontop of the `master` branch. If you want to do the opposite, use `--ours`.


#### Usage 2: `merge` conflict resolution
```sh
$ git co master
$ git merge testbranch
# encounter conflict here...
```
In this case, if we wanted to keep all changes for a file from the current branch `master` we use `git co --ours <filename>`. To do the opposite and keep the changes for a file coming from the `testbranch`, use `--theirs`.

#### What if there are multiple file conflicts?
If you have a lot of files conflicting in a `merge` or `rebase` situation, and you want to resolve all of them in the same manner, you can use a `strategy`. I'll cover strategies later on a separate TIL but for now, just note that its default algorithm is recursive. Given this, we can resolve conflicts for multiple files in the same manner by doing this for example:
```sh
$ git <rebase/merge> -s <ours/theirs> <yourbranch>
```




#### References:
- [Resolving conflicts with `git` with ours and theirs](http://inlehmansterms.net/2014/12/14/resolving-conflicts-in-git-with-ours-and-theirs/)
- [Keep either file in merge conflicts](http://gitready.com/advanced/2009/02/25/keep-either-file-in-merge-conflicts.html)
- [`git` resolve merge conflicts](https://easyengine.io/tutorials/git/git-resolve-merge-conflicts/)
- [Resolve conflicts during a pull](https://stackoverflow.com/questions/10697463/resolve-git-merge-conflicts-in-favor-of-their-changes-during-a-pull)

