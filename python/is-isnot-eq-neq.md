# `is`, `is not` vs `==`, `!=`

Simply put it, in python, `is` and `is not` operators are used for checking whether or not two things are identical whereas `==` and `!=` are used for checking whether or not two things are of equal value.

Identity checking verifies if two things point to the same thing. This is useful, as most references e.g. [PEP](https://www.python.org/dev/peps/pep-0001/#what-is-a-pep) put it, when comparing against singletons e.g. `None` (although there's debate on that; see [references](#references)).

Equality checking verifies if two things have the same value.

<br>
**Added info**:

Unfortunately, if you ever wondered whether Javascript's strict comparison operators, `===` and `!==` have python equivalents, they don't. The best way to mimic that behavior is using a combination of `isinstance` and `==` or the converse. (see [references](#references))

<br>
**References**:
- [python `none` comparison](https://www.appneta.com/blog/python-none-comparison/)
- [`!=` vs `is not`](http://stackoverflow.com/questions/2209755/python-operation-vs-is-not)
- [Difference between `!=` and `is not`](http://stackoverflow.com/questions/5782203/python-difference-between-and-is-not)
- [python strict comparison](http://stackoverflow.com/questions/28033852/strict-comparison)
- [`is None` vs `== None`](http://jaredgrubb.blogspot.com/2009/04/python-is-none-vs-none.html)

