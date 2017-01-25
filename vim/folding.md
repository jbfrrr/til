# Folding

Collapsing code, otherwise known  as 'Folding', is a very powerful and handy feature a lot of developers look for in IDEs. It's usefulness/convenience in large code bases/repositories is something indispensable. In my quest towards understanding and eventually migrating to Vim, I've already had multiple instances wherein I just wished I had folding setup. This is the document where I put what I've learned about folding so far...

As far as I've read, we can divide folding in vim into two levels, basic and advanced. TL;DR, you'll live/manage already with a lot of use cases just with the basic level...

* [Basic](#basic)
* [Advanced](#advanced)

For more details/info checkout other resources I've listed below

* [Resources](#resources)

---


####Basic

First and foremost, in order to use folding in vim, you need to specify what `foldmethod` to use.
There are six (6) different types of fold methods available:

* Manual - _usually defined by selecting a block `v` and hitting`zf`_
* Indent - _lines at the same indentation level fall in the same fold_
* Syntax - _folds based on syntax highlighting/language syntax_
* Marker - _similar to manual; uses special characters_
* Diff - _fold unchanged text when viewing diffs_
* Expr -_folds are defined by a user-defined expression_

For basics, we'll focus on 'Indent'. 

To set your fold method do:
```vim
" groups lines with the same indentation level
set foldmethod=indent
```

You can choose to have newly opened files already folded or unfolded
```vim
" to have code folded when opening a file
set foldenable

" else...
set nofoldenable
```

A good practice would also to guard against too many folds. You can set this by:
```vim
" maximum of 10 nested folds
set foldnestmax=10 
```

From here on, you can play around with the **folding commands**: 
```
" ESSENTIAL
zi	switch folding on or off
za	toggle current fold open/closed
zc	close current fold
zR	open all folds
zM	close all folds
zv	expand folds to reveal cursor

" MORE...
zj	move down to top of next fold
zk	move up to bottom of previous fold
zo	open current fold
zO	recursively open current fold
zC	recursively close current fold
zA	recursively open/close current fold
zm	reduce `foldlevel` by one
zr	increase `foldlevel` by one
```

**pro tip**: You can setup an alias for toggling folds e.g.
```vim
nnoremap <Space> za
```

####Advanced [TBA]


####Resources
* [vim.wikia: folding](http://vim.wikia.com/wiki/Folding)
* [stevelosh: folding](http://learnvimscriptthehardway.stevelosh.com/chapters/48.html)
* [vimcasts: how to fold](http://vimcasts.org/episodes/how-to-fold/)
* [vim101: folding](http://usevim.com/2012/08/31/vim101-folding/)
* [dougblack: fold](https://dougblack.io/words/a-good-vimrc.html#fold)