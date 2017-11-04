# Modifying remote url

If you wish to modify the remote url of a repository simply do:
```sh
# HTTPS
git remote set-url <remote_name> <https://github.com/new_remote.git>

# SSH
git remote set-url <remote_name> <git@github.com:new_remote.git>
```

If you want to delete a remote url simply do:
```sh
git remote rm <remote_name>
```
