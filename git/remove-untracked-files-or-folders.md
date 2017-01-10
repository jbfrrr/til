#Remove Untracked Files or Folders

Instead of manually removing unwanted untracked files, you can use:
```
git clean -f <path(optional)>
```
`-f` is to force git to delete files/directories if the git configuration variable `clean.requireForce ` is `true` (which is the case for most situations)
`path` is the starting point of the `clean` command where it will recursively delete files/folders. If not specified, the current directory you're in will be the starting point.

**pro tips**: Once you remove untracked files, it would be quite trick to get them back. To avoid this, you can see how your `clean` command will work by doing
```
git clean -fn <path(optional)>
```
`-n` is a dry-run and will only show you what will happen if you really execute the clean command

You can also run an interactive mode of `clean` by
```
git clean -fi <path(optional)>
```

**use cases**: Sometimes during development, you will realize you don't need some files that were added (intentionally/inadvertently) to be committed and/or pushed to the remote repository.

**context**: I was actually already familiar with this command before but forgot about it. I just happened to come across the command again while reading something and thought I'd note it down here.