# Detaching and Attaching to session
Let <prefix> be whatever your tmux control prefix is. In my case, it’s just the default, ctrl+b

To detach from a session, simply do:
```
<prefix> d
```
To attach to the last session, do:
```
tmux a
```
To specify a session to attach to, do:
```
tmux a -t <session name> // I believe -t stands for target session
```