#Kill 'unclosable' window

Sometimes something glitchy happens with [X11](https://en.wikipedia.org/wiki/X_Window_System) when closing windows e.g. it stops operating and it just won't close (regardless of what window manager you're using). This can be annoying at times.

To kill a seemingly 'unclosable' window, just do the ff:

1. Enter `xwininfo` on your terminal
2. You will be prompted to click on a window. Click the 'unclosable' one.
3. Information about the window will appear on your terminal including its `id`
4. Enter `xkill -id <window_id>`and you should be good!


For more info on the commands used, check their manuals:
```
man xwininfo # manual for xwininfo
man xkill # manual for xkill
```