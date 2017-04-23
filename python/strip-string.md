# `strip` String

Because I've wondered what python's equivalent to PHP's `trim`, I've thus gained yet another miniscule TIL entry...

`strip` is a built-in method of python's string datatype that you can call to strip trailing spaces from a string, much like PHP's  `trim`...
```py
s = " some string "
# remove whitespace on both ends
s.strip()

# remove whitespace on the right side
s.rstrip()

# remove whitespace on the left side
s.lstrip()

# strip space and any of the following characters \t, \n or \r
s.strip("\t\n\r")
```
