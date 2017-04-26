# `empty` quirk

A frequently used PHP function is `empty`. It's mostly used to check if an array has no elements or if something does not exist / is falsey. It's the equivalent of:
```php
!isset($var) || $var == false
```

**BUT IT HAS A QUIRK!** [Prior to PHP 5.5, `empty` only supports variables!](http://stackoverflow.com/questions/22616264/why-does-this-causes-an-error). Below is an example which will yield a parse error for anyone using < PHP 5.5: 
```php
...
if (empty($this->obj->getArray())) {...}
...
```

**context**: I relearned this when we pushed a feature/tool that had a similar use case to the example above. It was working fine on dev, but not in production. _sigh, dev-prod inconsistencies..._

