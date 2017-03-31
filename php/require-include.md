# `require` vs `include`

First, `require` and `include` are PHP functions used to combine and/or evaluate statements/code from other files allowing for code distribution and isolation of responsibilities.

_So what's the catch? Why two functions?_

`require` is the same as `include` but in the instance that it fails to incorporate a file, it emits a **FATAL** `E_COMPILE_ERROR` thus immediately terminating all execution at that failure point.

On the other hand `include` only fires an `E_WARNING` which still permits execution to continue.

_What about `require_once` and `include_once`?_

`require_once` and `include_once` have pretty much the same behavior as `require` and `include` respectively as described above, only that they make sure that once you've incorporated/evaluated the file, it doesn't get added/executed again (_even if the code somehow loops back into that specific line where you required or included it_)

For more info, check this [stackoverflow thread](http://stackoverflow.com/questions/2418473/difference-between-require-include-and-require-once)
