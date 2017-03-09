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
Doing `sudo pm-hibernate` saves your machine's state to disk (secondary memory) and will turn off your machine entirely. The good part here is that your machine can stay in hibernate mode for an indefinite amount of time. However, recovering from hibernate state requires more time (~15-45 seconds)

### `pm-suspend-hybrid`
---
Think of this as the "middle ground" of the previous two functions, balancing bootspeed and fail-safe convenience. `sudo pm-suspend-hybrid` sets the machine to be ready to hibernate in case the machine runs out of power, making sure to save its state to disk. However, unlike `pm-hibernate` it does not completely shutdown the machine thereby allowing recovery from this hybrid suspension to be much faster (i.e. as long as the machine still has power left...)

<br>
<br>
<br>
**additional info**: For `pm-suspend` and `pm-suspend-hybrid`, you can add args after the command. These args are known as [`quirks`](https://linux.die.net/man/8/pm-hibernate), Basically they allow you to specify some specific/special handling of certain hardware upon entering these states.
