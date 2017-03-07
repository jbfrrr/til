# Browser History API

... <sub>`WIP`</sub>

In some cases, you'd like to add state to your AJAX application. That is, as you dynamically add/remove content from your page, you'd also like to change the URL without reloading the page. The browser history API allows us to do that by just doing:
```js
/*
window.history.pushState(<object/string>, <title>, <new_url>)
    arg1 <object/string> is the object/string you pass into the state
        that you can use to manipulate state
    arg2 <title> explains the state of the DOM at that point to the user
        Does NOT change the <title>
    arg3 <new_url> is the URL that the browser have/change to
*/
window.history.pushState('', document.title, '/new_url')
```

**Resources**:

* [Web history API](https://developer.mozilla.org/en-US/docs/Web/API/History_API)
* [HTML5 history API](https://developer.mozilla.org/en-US/docs/Web/API/History_API)
* [Changing browser URL `w/o` refresh](http://spoiledmilk.com/blog/html5-changing-the-browser-url-without-refreshing-page/)
