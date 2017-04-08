# Disabling elements

There are a couple of ways to disable elements in your DOM if they have the `disabled` attribute.

In AngularJS `v1` we have [`ng-disabled`](#ng-disabled).

In AngularJS `v2` we can leverage [[`disabled`] property binding](#property-binding)

Let's take a button as our example for both old and new AngularJS.

### `ng-disabled`
```html
<button ng-disabled="MyComponent.isDisabled">Next</button>
```

### `[disabled]`
```html
<button [disabled]="isDisabled">Next</button>
```

### References
- [`ng-disabled` directive -ngjs.org](https://docs.angularjs.org/api/ng/directive/ngDisabled)
- [`ng-disabled directive -w3`](https://www.w3schools.com/angular/ng_ng-disabled.asp)
- [Alternative to `ng-disabled` in Angular2](http://stackoverflow.com/questions/37159827/is-there-any-alternative-for-ng-disabled-in-angular2)

