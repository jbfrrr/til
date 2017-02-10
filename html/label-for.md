# The purpose of`for` in a `<label>` tag

The `label` tag helps users identify an element in the UI. It serves like an element's caption.

For example:
```html
<!--label helps users identify what the input box is for-->
<label for="name">Name</label>
<input type="text" id="name" class="form-control">
```

The `for` attribute, when added to a `label` tag, allows us to associate the `label` to the element it's trying to help users understand.
What association does in this case is really more of improving accessibility i.e. when the user clicks the `label`, the response to that action is toggling the control to the element.

So, for the previous example, if a user clicks on 'Name', the input box then becomes active and the user can start typing.

**Note** that in order to make this work, it is important that the value assigned to `for` is the same as the `id` of the element to be associated with. An alternative to the use of `for` for association is defining the associated element within the `label` tag. For more details, check [MDN's `label` doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)

**context**: I learned this because I've been doing some front-end work lately and just got curious. I usually stick to back end, but improving something I'm weak at is always welcome!

