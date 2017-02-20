# `pm-utils`

Here's a scenario, You have lots of stuff setup in your workstation from tmux sessions and remote terminal connections, to multiple browsers and tabs open, but, you need to leave your machine idle for an indefinite amount of time without having to do all the initial steps you did on boot and, without having to spend much of your machine's energy!

What to do !?!?

**Do not fear!**

Power Management Utils a.k.a. [`pm-utils`](https://wiki.archlinux.org/index.php/pm-utils) to the rescue!

There are a number of ways to address the given scenario above and `pm-utils` provides a couple of basic and useful commands at your disposal:


### `pm-suspend`
---
Doing `sudo pm-suspend` will turn off your machine's cpu and most of its other components / devices but makes sure to keep the memory (RAM) powered as it saves your machine's state there. Recovering from this state is relatively quick (~3-5sec) but if your machine somehow runs out of power, the state which you left it (including all your configs) will be lost.

### `pm-hibernate`
---
[wip]

### `pm-suspend-hibrid`
---
[wip]
