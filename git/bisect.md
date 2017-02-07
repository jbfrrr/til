# `bisect`

Trouble finding where and when a bug was introduced that got things broke?

Well, git has a tool / feature just for that!

Enter `bisect`! Find that bug using binary search on your commits!

To use it, you just have to:

1. Identify a 'bad' commit, and a 'good commit'
2. Test the commit git checks out for you (i.e. the middle of the 'bad' and 'good' commits)
3. Iterate until you find the commit where things broke

Below is some code to show what I mean:
```sh
# Step 1: assuming the current HEAD is broken
# specify that the commit hash is broken i.e. 'bad'
git bisect start
git bisect bad

# Step 2: checkout a good commit
# tell git that it's all good on that commit i.e. 'good'
git checkout <supposedly good commit>
git bisect good

# Step 3: git will then checkout out the middle of the 'bad' and 'good' commits
# it will return something like...
Bisecting: X revisions left to test after this (roughly Y steps)
[xxxxxx] Commit Message

# Step 4: test this commit and identify whether it's 'good' or 'bad' again.
# iterate until you're left with
# the one 'bad' commit (where bad things started to happen)

# Step 5: once you've found it,
# reset bisect to return to the commit you checked out
# before doing `git bisect start`
git bisect reset

# Step 6: resolve the bug in the way you see fit
```


**Additional tips**: Alternatively, right after doing `git bisect start` you can identify the 'good' and 'bad' commits by:
```sh
git bisect bad <commit_hash(A)>
git bisect good <commit_hash(B)>
```

