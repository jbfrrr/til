# Template Literals

In ES6, template literals are string literals that allow embedded expressions, e.g. multi-line strings and [string interpolation](https://en.wikipedia.org/wiki/String_interpolation). Instead of your usual strings which are enclosed by single or double quotes, template literals use back-ticks instead.

The following code below show basic/common example use cases:
```js
// print 'Hello World'
console.log(`Hello World`);

// print 'Hello' and 'World' on separate lines
console.log(`Hello
World`);

/*
concatenate and evaluate
prints "There are 5 rooms and 100 participants. We can have 20 participants per room."
*/
let rooms = 5;
let participants = 100;

console.log(`There are ${rooms} rooms and ${participants} participants. We can 	have ${participants / rooms} participants per room.`)
```