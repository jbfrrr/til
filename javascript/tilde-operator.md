# Tilde Operator

**TL;DR**: For most cases, you can live without knowing this 'clever' operator. To be fair though, it felt pretty cool to have learned about this, hence me adding it to my TIL list. Read on if you're interested...

`~` in javascript is a bitwise NOT operator, i.e. it converts its operand into an integer, represents it as binary, and flips all its bits. A much simpler way of interpreting/visualizing this is that it does the ff to its operand, say `x`:
```js
~x = - (x + 1)
```
A common cited use case for a single `~` would be a more concise way of checking whether the sentinel value of a function is true or false, e.g. `indexOf`:
```js
var myStr = 'test';

if (~str.indexOf('a')) {
    // found it. do code that's necessary here...
} else {
   // didn't find it. do code for this case...
}
```
Going a bit further, doubling the `~` would simply convert the operand to an integer, removing everything after the decimal point. The effect is similar to `Math.floor` for positive numbers and `Math.ceil` for negative numbers (effectively making `~~` like `Math.trunc`)

