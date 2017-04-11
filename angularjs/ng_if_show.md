# `ng-if` vs `ng-show`

TL;DR the question you need to ask to know which directive to use is:

"Is the element you wish to apply any of these directives something you want to keep in the DOM or not?"

This is because, the main difference between `ng-if` and `ng-show` (alternatively `ng-hide`), is that the former removes the element its attached to if the expression assigned to it evalutes to `true` while the latter just adds `css` to conceal the element.

**additional details**

### `ng-if`
- if the element is removed by this directive, a new `scope` is created when the element is restored
- if you use `ng-if` inside `ng-model`, in order for you to modify the value of a variable from the parent scope, you must [use an `object` or reference the `$parent`](http://stackoverflow.com/questions/19177732/what-is-the-difference-between-ng-if-and-ng-show-ng-hide)

### `ng-show`
- `ng-hide` works the same; just the negative
- uses `.ng-hide` `css` class with `!important`, defined in AngularJS, to hide the element
