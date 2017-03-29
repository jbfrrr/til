# `grep` multiple patterns

First of, if you don't know what `grep` is, backlog this TIL for a bit, open a terminal and `man grep` first. LOL

So for a lot users and use cases, you can live by using `grep` for a single pattern.

However, it can't be denied that using `grep` for multiple patterns comes in handy in common instances as well.

For this TIL, I'll put in my context as a web developer. Say I want to monitor my logs and I want to see only warnings and errors. To do this with `grep` we would have something like:

```sh
tail -f log.txt | grep -iE 'warning|error'
```
Some notes on the command combination above:

- `tail` gets the ending parts of the log file. `-f` option follows the log file as it grows thus outputting newer logs that get inputted into the log file as it updates
- `i` option for `grep` tells `grep` that the following pattern should be evaluated case-**insensitive**, while `E` for `grep` tells `grep` that the pattern should also be evaluated as an [extended regular expression](http://unix.stackexchange.com/questions/17949/what-is-the-difference-between-grep-egrep-and-fgrep).


