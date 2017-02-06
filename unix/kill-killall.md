# `kill` & `killall`

**Avada Kedavra!** Yes this is exactly what popped in my head back in second year college when I first learned about the `kill` command in our OSs and Computer Architecture class.

HP analogies aside, the `kill` command is exactly what you need to get rid of processes that consume too much resources or have become unresponsive.

`kill` expects a process id (PID) to be passed to it. This PID represents the id of the process that you wish to terminate. You can acquire this info using `ps`, `top` or other similar commands.
```sh
kill 2017 # where 2017 is some cron process
```

But that's old knowledge. The new things I've learned here today would actually be a similar command `killall` and how `kill` and `killall` works.

`killall` does what `kill` does but it can do it for multiple process. Instead of passing a PID, you pass a process name and `killall` will attempt to terminate all processes with that name.
```sh
killall subl # attempt to kill all process with `subl` name
```


`kill` and `killall`, by default send the `TERM` signal to the process(es) to be killed. `TERM` is the signal that tells a process to terminate in the most graceful manner that process knows how (_i.e. if needs to do some clean up first, etc._).

But what if the process still won't die? Well you can harness the full power of `kill` or `killall` by doing any of the ff:
```sh
# in this example only `kill` is used, but you can do the same for `killall`

# force terminate
kill -KILL 2017

# does the same thing as -KILL...
kill -9 2017
```

**pro tip**: Always try the gracefull `kill` or `killall` first!
