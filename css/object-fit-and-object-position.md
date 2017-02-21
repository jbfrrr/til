# `object-fit` & `object-position`

Need css to solve your problem of fitting images nicely inside a container?

`object-fit` & `object-position` are the answers!

Basically `object-fit` takes care of how an image appears based on the height and width of its container (i.e. whether it crops, stretches, squishes).

On the other hand, `object-position` allows us to define how an image is placed within its container (i.e. `x` and `y` values relative to the container).

We can choose to use the two css properties separately or together.

As much as I'd like to provide examples of my own here on how to use these css properties, I believe the visuals that online articles/blogs/sites provide would be more helpful so here are some references:

* [Codepen Sample](https://codepen.io/dudleystorey/pen/myPZwN)
* [Quirks Mode Sample](http://www.quirksmode.org/css/images/object.html)
* CSS Tricks:
    * [`object-fit`](https://css-tricks.com/almanac/properties/o/object-fit/)
    * [`object-position`](https://css-tricks.com/almanac/properties/o/object-position/)

Just glanced? Here's a brief summary:

`object-fit` can be set with any of the ff values:

* `object-fit: fill` stretches the image to fit the container without regard for the image's aspect-ratio.
* `object-fit: contain` will try its best to fit the container by increasing/decreasing the image's height/width while preserving the aspect-ratio. If you use this, you might still end up with dead space length/width wise
* `object-fit: cover` will fit the image in the container nicely while maintaining aspect-ratio; however it may be cropped. This is likely **what you're looking for!**
* `object-fit: none` does nothing to the image
* `object-fit: scale-down` sets the image to the smallest object size possible by comparing the difference of `none` and `contain`

`object-position` just needs two (**percentage**)values, `x` and `y`. So you have something like
```css
img {
    object-position: 50% 50% // this is the default setting btw
}
```

<br>
<br>
**Caveat!** `object-fit` and `object-position` have browser support issues, most notably for IE/Edge. Please make sure to recheck support online before using it in your project. Here's a curated list of some polyfills you can use:

* [bfred-it/object-fit-images](https://github.com/bfred-it/object-fit-images)
* [anselmh/object-fit](https://github.com/anselmh/object-fit)
* [Neat css trick for object-fit-fallback](https://medium.com/@primozcigler/neat-trick-for-css-object-fit-fallback-on-edge-and-other-browsers-afbc53bbb2c3#.qct9bo6se)
