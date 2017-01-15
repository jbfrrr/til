#`core.autocrlf`

TL;DR if you're working on project on Linux/Mac and you're working with other people who are not (e.g. Windows) then you ought to know this...

Setting `core.autocrlf` correctly on your project's git config or your global config is most useful for the given scenario above because you will save yourself the trouble of dealing with line-ending issues. To be more specific:

- Windows uses `carriage-return` + `line-feed` (CRLF)
- Linux/Mac use `line-feed` (LF) only

The setup below will leave you with CRLF endings in Windows checkouts but LF endings on Linux/Mac. (_note, the cases below use the global config; restrict to local repo if you want_)

Windows
```
# this converts LF into CRLF
git config --global core.autocrlf true
```

Linux/Mac (and the like...)
```
# converts CRLF to LF on commit
git config --global core.autoclrf input
```
