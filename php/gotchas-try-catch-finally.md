# Gotchas: `try-catch-finally`

#### `finally` executes before leaving `try-catch-finally` block
```php
class MyCustomException extends Exception {}
class OtherCustomException extends Exception {}

function myFunction() {
    try {
        echo "1\n";
        throw new OtherCustomException();
    } catch (MyCustomException $e) {
        echo "2\n";
    } finally {
        echo "3\n";
    }
}

try {
    echo "4\n";
    myFunction();
    echo "4.5\n";
} catch (OtherCustomException $e) {
    echo "5\n";
} finally {
    echo "6\n"
}

// OUTPUTS
// 4
// 1
// 3
// 5
// 6
```

#### "`return` before `finally`" weird behavior
TL;DR if you have a `return` in the `try` or `catch` block, as long you have a `finally` block, the `finally` block code will still execute before your  `return`
```php
function myFunction() {
    try {
        echo "1\n";
        throw new Exception();
    } catch (Exception $e) {
        echo "2\n";
        return;
    } finally {
        echo "3\n";
    }
}

myFunction();

// OUTPUTS
// 1
// 2
// 3
```

#### `finally` comes in only at v5.5+
For PHP versions lower than 5.5, if you don't need the added functionality of `finally` described above, and, just need code to execute after entering the `catch` block, assuming there's no `return` statement or the like inside the `catch` block, then just add the code to be executed right after the catch block.

#### Catching exceptions in non-root namespace
```php
namespace MyTest;

// You need to indicate you're using the Exception class!
// Otherwise you'll get a runtime error
use Exception;

try {
    echo "1\n";
    throw new Exception();
} catch (Exception $e) {
    echo "2\n";
    return;
}
```


#### Object thrown must always be an instance / subclass of Exception
> The thrown object must be an instance of the Exception class or a subclass of Exception. Trying to throw an object that is not will result in a PHP Fatal Error.




References:
- [PHP 5.5 `try-catch-finally`](https://adayinthelifeof.nl/2013/02/12/php5-5-trycatchfinally/)
- [PHP Manual: Language Exceptions](http://php.net/manual/en/language.exceptions.php)
- [Silent failure to catch exceptions](http://yakhairsurplus.com/silent-filure-to-catch-exceptions-in-php/)
