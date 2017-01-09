# Spread Operator (a.k.a Rest Operator)

`...` or the spread operator is an ES6 feature that allows the expansion of an expression where multiple arguments (e.g. functions) or multiple elements (e.g. arrays) or multiple variables (destructure; a.k.a rest operator) are expected.

**use case 1: Functions**
```
function testFunction(x, y, z) {
    console.log(x+y+z);
}
let args = [90, 92, 93];
testFunction(...args); // 275
```

**use case 2: Arrays**
```
let x = [1,2,3];
let y = [11,13];
console.log([...x,5,7,..y]); // [1,2,3,5,7,11,13]
```

**use case 3: Variables** (_note: The use of the spread operator here is more known as the use of the rest operator, i.e. it does the opposite of the spread operator. Instead of expanding elements, it collects multiple elements and condenses it into one)_
```
function testLength(...xargs) {
    console.log(xargs.length);
}
testLength([1,2,3,4,5]); // 5
```

**note**: For more detail/resources check the ff:

* [MDN Spread Syntax](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Spread_operator)
* [three-dots-javascript-spread-operator](http://jpsierens.com/three-dots-javascript-spread-operator/)

