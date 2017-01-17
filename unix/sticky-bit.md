# Stick Bit

If you want to prevent users (other than the owner/root)  from deleting/renaming a folder and its content, you can add the `Sticky Bit` to the permissions of that folder.

You can place the `Sticky Bit` using different methods. Below are a couple of ways to do so.
```sh
# symbolic method
chmod +t <directory>

# octal method; `1` is the sticky bit
chmod 1777 <directory>
```

Once, the `Sticky Bit` is assigned to a directory, its permissions could look something like this:
```sh
# `t` is the sticky bit part
# note that even if all users have rwx rights, they still can't rename/delete files 
# unless they're they owner of the directory or they're root
drwxrwxrwt
```

**Additional Info:**
In some cases you'll see `T` instead of `t` in the files permissions. What this means is, though both files still indicate the presence of the  `Sticky Bit`...

* if it's `T` that's set, it means not all users have `executable` or `x` permission/rights
* if its `t` that's set, it means all users have `executable` or `x` permission/rights

Also, setting the `Sticky Bit` for files is allowed but is pretty much useless...

