# Arrow Functions

TL;DR **Arrow Functions**, introduced in ES6,  are basically anonymous functions written in a more concise manner and do not bind to its own `this` (i.e. `this` will always refer to the current context no matter how many anonymous arrow functions are nested in a class).

It also doesn't bind to its own `arguments`, `super` or `new.target`. Although I won't cover these anymore here as well as other nitty gritty stuff, complete details about arrow functions can be found [here](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Functions/Arrow_functions)

The best way I understood the basics of arrow functions is through a set of relatable examples/use cases that show its benefits. Let's do that...

**Sample 1**: More concise...
```js
// traditional way of defining functions prior to ES6
var cubeV1 = function (a) {
    return a*a*a;
}
cubeV1(2); // outputs 8

// ES6 arrow function version...
const cubeV2 = (a) => {
    return a*a*a;
};
cubeV2(2); // outputs 8

/* ...even shorter
 note this only works if you just want to return a value immediately
 notice you don't need 'return' anymore because that's implicit for one line arrow functions
 */
const cubeV3 = (a) => a*a*a;
cubeV3(2); // outputs 8

/* ...shorter still
 note this only works if you have only one parameter passed (of course you can pass multiple params)
 */
const cubeV4 = a => a*a*a;
cubeV4(2); // outputs 8
```

**Sample 2**: Doesn't bind to `this`...
```js
// tranditional way of applying anonymous functions with OOP
function Timer(x) {
	this.startTime = 0;
	var self = this; // had to be done or else `this` inside setInterval will bind to window
	setInterval(function() {
		self.startTime += x;
		console.log(self.startTime+'sec have passed -- Timer'):
	}, 3000);
}
var timer = new Timer(3);

// ES6 way...
function TimerES6(x) {
	this.startTime = 0;
	setInterval(() => {
		console.log(`${this.startTime += x}sec have passed -- TimerES6`);
	}, 3000);
}
let timerES6 = new TimerES6(3);
```

**context**: I learned more about this in the past couple of days since I had to migrate legacy JS (using RequireJS) to ES6