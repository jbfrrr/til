# Directive _asterisk_ `*` prefix

TL;DR, the reason why we prefix an asterisk `*` to directives we place in HTML elements like `ngIf`, `ngFor` or `ngSwitch` or even a custom directive of our own, is because it's the simpler and implicit way of telling Angular to wrap the element in `<template>` tags. The wrapping is a requirement for these directives because their actions rely on doing something with the `<template>`.

```html
<!-- how we write it -->
<p *sampleDirective="sampleExpression">Sample Message</p>

<!-- what Angular does under the hood...-->
<!-- step 1 -->
<p template="sampleDirective sampleExpression">Sample Message</p>

<!-- step 2 -->
<template [sampleDirective]="sampleExpression">
  <p>Sample Message</p>
</template>
```

Notice that:

* the directive moved to the `<template>` tag, becoming a property binding, `[sampleDirective]`
* the original element (not shown but including its other attributes) moved inside the `<template>` tag

Furthermore, in the final rendering in the DOM, what would just appear would just be the final result of the directive's action on `<template>`; i.e. `<template>` won't be part of the DOM when you inspect it...

For more details check:
* [The Asterisk Prefix](https://angular.io/docs/ts/latest/guide/structural-directives.html#!#asterisk)
* [Angular Cheatsheet](https://angular.io/cheatsheet)
* [The magic behind `*`](https://mytechnetknowhows.wordpress.com/2016/08/07/angular-2-ngfor-whats-the-magic-behind-asterisk-and-other-mysteries/)
