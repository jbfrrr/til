# "Poorman's" Ternary Operator

TL;DR bash **HAS NO** ternary operatory, unfortunately...

Here's a close, but poor / failed attempt at mimicking a ternary operator in bash:
```sh
if [ $isValid ]; then x=1; else x=0; fi
```

As you can see, this isn't really how a ternary operator should work. Bash only went as far as copying how it looks, lol.

Also, notice that unlike other ternary operators in languages such as PHP, C, Java, Javascript, which allow the ternary operator to come after an assignment e.g.,
```js
x = isValid ? 1 : 0;
```

bash's attempt requires that an assignment expression is provided after its `then` and/or `else` blocks...

