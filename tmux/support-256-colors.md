# Support 256 colors

There are a couple of ways to make your tmux sessions support 256 colors for instance using a `conf` file or other hacky stuff. 

The easiest and most compatible way I found to do this is just start your tmux session with `-2` at the beginning. So for example, you have something like:
```
tmux -2 new -s <session_name> // -2 tells tmux to assume support for 256 colors. see `man tmux`
```

**tip**: You can also alias tmux to `tmux -2` already so you don't even have to think about adding  `-2` everytime you make a session.

**use case**: The most common use case for this is when you're using vim alongside tmux, i.e. if you don't tell tmux to assume support for 256 colors, your vim colorschemes might not work.
