# Using system clipboard

Have you ever wanted to share code you had but you're using `vim` and you couldn't figure out how to do it properly? And, in the process, felt this was such a let down of an editor you loved?

Well, TIL, you can actually leverage your system's clipboard through `vim` and thus be able to share code with others just the way you see it!

By default `vim` uses its own buffer for storing 'yanked' lines called the 'unnamed register'. For us to be able to use the system's clipboard we should first check if our `vim` version supports this

*note: I'm on Ubuntu so there might be a different way for your system*
```sh
vim --version | grep clipboard
```

If your `vim` supports using the system clipboard you must at least see `+xterm_clipboard` or `++clipboard` after executing the code above in your terminal. If you don't you might need to do
```sh
sudo apt-get install vim-gtk
```

When your vim already supports `clipboard` you can now explicitly let `vim` know when to 'yank'/copy lines into your system's keyboard by selecting the lines you wish to copy (in visual mode ofcourse) and doing
```
"+yG
```

Now when you do `ctrl+v` on any other place/editor, you'll see the code you've just copied formatted exactly how you copied it!

Now, go forth and share code!


##### References:
- [Accessing the system clipboard](http://vim.wikia.com/wiki/Accessing_the_system_clipboard)
- [How to make vim paste from and copy to systems clipboard](https://stackoverflow.com/questions/11489428/how-to-make-vim-paste-from-and-copy-to-systems-clipboard)
- [How can I copy text to the system clipboard from vim](https://vi.stackexchange.com/questions/84/how-can-i-copy-text-to-the-system-clipboard-from-vim)
