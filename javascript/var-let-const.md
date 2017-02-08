# `var`, `let`, `const`

TL;DR for ES6 code, when declaring variables:

* use `const` by default
* if you need to reassign / rebind, use `let`
* avoid using `var` in ES6

`var`, `let`, `const` are ways we can declare variables in javascript. Back in the day, it was just `var`, but come ES6, we have `let` and `const`.

So what's the 'diff' you might ask? We lived with `var` right?

The main 'diff' my friend, is **Scoping**.

* `var` is function scoped
* `let` and `const` are block scoped

What does this exactly mean?
```js
const multiplier = 5;
for (let i = 1; i <= 10; i++) {
	var x = i * multiplier;
	console.log(`${i} x ${multiplier} = ${x}`); // an output here would look like "1 x 5 = 5"
}
console.log(x); // outputs 50; x is visible anywhere since it was declared...
console.log(multiplier); // outputs 5; this is because multipler scope is on window
console.log(i); // uncaught reference error: i is not defined; i is not visible in this scope
```

Aside from that, `let` and `const`allow you to declare a variable inside its scope only once, while `var` just allows you to do that (this is not exactly a good thing since you're more susceptible to accidental mistakes).
```js
function testRedclareLet() {
	let x = 1;
	let x = 2; // will fail here
}

function testRedeclareConst() {
	const x = 3;
	const x = 4; // will fail here
}

function testRedeclareVar() {
	var x = 5;
	var x = 6; // valid
}
```
Furthermore, a variable declared using `let` can be updated, while a variable declared using `const` cannot. Using a similar example previously:
```js
const multiplier = 5;
for (let i = 1; i <= 10; i++) {
	console.log(i * 5);
	multiplier++; // will fail here
}
```
...which leads me to one common misconception about `const`, i.e. "it's immutable". One counter example to this would be the fact that we can declare an object as `const` but still change its properties.
```js
const human = {
	name: Joe,
	age: 18,
	weight_lbs: 140
}
human.age = 23; // valid
human.weight_lbs = 160; // valid
```

One more cool / interesting thing to note would be the advantage of using `let` vs `var` in closures within loops. For example, the code below will output '10' ten times. This is because `i` here is in the **global scope** and because the callback is **asynchronous**, letting the loop complete before any are executed.
```js
for (var i = 1; i <= 10; i++ ) {
	setTimeout(function() {
		console.log(i);
	}, 1000);
}
```
By simply changing `var` to `let` in this case, we allow each value of `i` to bind to the callback for each iteration of the loop (_i.e. each value of `i` is scoped in the loop_), thus printing a count from 1 to 10.

**Retrospect**: Before ES6, the fix to the previous issue was to wrap the global variable `i` within another closure that allows us to capture the value of `i` in each iteration. See examples from this awesome [blog post](http://www.datchley.name/loop-variable-gotcha/) by Dave Atchley



For more info / detail, see the resources I've listed below:

* [What's the difference between using `let` and `var` to declare a variable?](http://stackoverflow.com/questions/762011/whats-the-difference-between-using-let-and-var-to-declare-a-variable)
* [ES6 `const`](https://mathiasbynens.be/notes/es6-const)
* [`var` vs `let`](http://www.jstips.co/en/keyword-var-vs-let/)
* [`let` vs `const`](http://wesbos.com/let-vs-const/)
