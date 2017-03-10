# Clear Bash History

So you've accidentally typed your password on your terminal in plain text for anyone to see --- _maybe the password prompt hasn't loaded yet_

Or perhaps, you've just entered a few dangerous commands on the terminal while using a shared account.

What do you do?

**CLEAR YOUR BASH HISTORY!**

#### View Your History
But before we dive into clearing your bash history, you must first know how to view it.
Just type and enter:
```sh
history
```

Ok cool! You've got it

Now, let's clear some commands.

There are actually a couple of ways you can clear your bash history...

#### Clear All Terminal History

To clear all of the commands you've just entered in a terminal, do:
```sh
history -c
```

#### Delete Specific Command From Terminal History

To delete a particular command you've done before, simply type and enter:
```sh
history -d <command_number> #note you can see the command number when you print the history
```

#### Skip Saving a Command In History

To prevent saving a command you're about to execute, just add a `<space>` before the command.
For example:
```sh
<space> echo "hello"

history # echo "hello" won't appear in the list...
```

#### Delete History For All Terminals

Note that there's a slight catch with the above methods. The problem with the previous methods is that you're only removing commands from the history of the terminal you're currently using.

In order for you to delete the history for all terminal sessions you can do any of the ff:

1. Manually delete `~/.bash_history` each time you deem its time to 'clean up'
2. Schedule a cron job to periodically delete the `~/.bash_history`
