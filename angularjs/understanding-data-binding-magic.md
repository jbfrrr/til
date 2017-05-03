# Understanding Data Binding Magic<sub>`WIP`</sub>

Long story short, it seems AngularJS uses `dirty checking` to know when to re-evaluate expressions
inside directives like `ng-show`. This only means, in a basic / general sense, AngularJS stores the values that make the expression, and if any of these values change, it re-evaluates the expression.

For example, if we have
```html
<div ng-show="Card.test === 'true' && Card.input.length > 0">
  ...
</div>
```
if `Card.input.length` changes, `ng-show` re-evaluates the entire expression assigned to it. Additionally, if we store this expression inside a function of the component/directive encompassing the html template code above, it will still re-evaluate if either `Card.test` or `Card.input.length` changes values.


References:
- [How does data binding work in AngularJS ?](http://stackoverflow.com/questions/9682092/how-does-data-binding-work-in-angularjs/9693933#9693933)
- [Is expression inside `ng-show` fired after every model change in AngularJS ?](http://stackoverflow.com/questions/15189742/is-expression-inside-ng-show-fired-after-every-model-change-in-angularjs)
- [What you need to know about AngularJS Data Binding](https://thecodebarbarian.wordpress.com/2014/01/31/what-you-need-to-know-about-angularjs-data-binding/)
- [How two way data binding works in AngularJS](https://cfdeepak.wordpress.com/2014/09/29/how-two-way-data-binding-works-in-angular-js/)
- [The magic of AngularJS two-Way binding](http://moduscreate.com/the-magic-of-angular-js-two-way-binding/)
