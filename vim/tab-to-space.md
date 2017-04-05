# Tab-To-Space

The example below converts a file with two space indentation to use four space indentation format:

**Step 1**: Make sure the entire file does follow two space indentation format consistently

```vim
:set tabstop=2 "tab size equals 2 spaces
:set softtabstop=2 "use 2 spaces when you hit tab/backspace in insert mode
:set shiftwidth=2 "indentations `<<` or `>>` equals the size of 2 spaces
:set noexpandtab "use real tabs, not spaces
:retab! "replace all space-tabs with real tabs
```

**Step 2**: Convert all real tabs to 4 spaces

```vim
:set tabstop=4
:set softabstop=4
:set shiftwidth=4
:set expandtab "replace tabs to spaces
:retab "reformat the entire file using the new tab-space rules
```

Alternatively, you can do this in one line:
```vim
:set ts=2 sts=2 sw=2 noet | retab! | set ts=4 sts=4 sw=4 et | retab
```

To do the opposite, i.e. convert spaces to tabs, just do the reverse!

References:
- [Retabbing in Vim](http://ppanyukov.github.io/2011/06/29/retabbing-in-vim.html)
- [Converting tabs to spaces](http://vim.wikia.com/wiki/Converting_tabs_to_spaces)
- [Change two spaces indent to four space in vim](http://stackoverflow.com/questions/16888658/change-2-space-indent-to-4-space-in-vim)
- [vimrc](http://www.apaulodesign.com/vimrc.html)


