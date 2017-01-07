# Go to start or end character of a line

First, make sure you're in `NORMAL` mode.

**Starting...**

* To go to the first non-blank character of the line, simply press `^`.
* To go to the first character of the line, you can press either `0` or the `<Home>` key.
* On the other hand, pressing `g`+`^`, goes to the leftmost non-blank character in two different ways depending on whether your vim setting wraps or doesn't wrap the text. `g`+`0` or `g`+`<Home>` key works similarly, but this time captures blank characters as well.

**Ending...**

* To go the last character of the line, simply press `$`
* On the other hand, pressing `g`+`$`, goes to the rightmost character in two different ways depending on whether your vim setting wraps or doesn't wrap the text.