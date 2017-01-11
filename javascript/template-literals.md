# Template Literals

In ES6, template literals are string literals that allow embedded expressions, e.g. multi-line strings and [string interpolation](https://en.wikipedia.org/wiki/String_interpolation). Instead of your usual strings which are enclosed by single or double quotes, template literals use back-ticks instead.

The following code below show basic/common example use cases:
```
# print 'Hello World'
`Hello World`

# print 'Hello' and 'World' on separate lines
`Hello
World`

# concatenate and evaluate
# prints "There are 5 rooms and 100 participants. We can have 20 participants per room."
var rooms = 5;
var participants = 100;

`There are ${rooms} rooms and ${participants} participants. We can 	have ${participants / rooms} participants per room.` 
```