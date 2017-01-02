#Use Repository Specific User Config

The following commands will ensure that Git will explicitly ask you to set `user.name` and `user.email` on a per-repository basis.

```
# Requires you to set user.name and email per repository
git config --global user.useConfigOnly true
#Remove email address from global config
git config --global --unset-alluser.email
```

**context**: I learned this because I have multiple github accounts and I want to make sure I commit using the right username and email address per repository.

**note**: There are other possible ways to achieve this behavior but this is the one that works most conveniently for Git v2.8 and above

