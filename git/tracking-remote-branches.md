# Tracking remote branches

#### Why (?)
Simple... Because it **makes your life easier**.

Let's say you have multiple local branches inside a repository named _X_, e.g. _dev_, _staging_, _production_, each of which also has a counterpart remote branch in your github remote repository _X_.

If you tracked the remote branches accordingly, pushing and pulling is so easy as you can just use `git push` and `git pull` without having to worry about specifying the remote repository and the branch you wish to pull/push to/from. Also, git can tell you about the state of your local branch i.e. whether you have any 'unpushed' or 'unpulled' stuff.

To know what your local branches are tracking, do:
```sh
git branch -vv
```

#### How (?)
```sh
# use case 1:  Working on an existing remote branch (production)
git checkout --track X/production

# use case 2: Pushing a new local branch (staging)
git push -u X/staging

# use case 3: When you forgot...(dev)
git branch -u X/dev
```

For more details, you can checkout this [short article/blog post](https://www.git-tower.com/learn/git/faq/track-remote-upstream-branch)








