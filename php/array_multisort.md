# `array_multisort`

**context**: Okay... so the only reason I had to put this here on my TIL is because this is one f***ed up function IMO. Yes it's quite useful, if you know how it works, but, I don't think it's intuitive enough to understand at a glance. I encountered this built-in php function while I was reviewing code...

Let's break it down with an example.

Say we have array of users who are represented by their `user_ids` and another array representing the users' corresponding `ratings`.

Say we wanted to sort the users by their ratings in descending order, and, if they're equal, sort them by their ids in ascending order.

You still with me?

If so then, as you might guess, `array_multisort` allows us to do just that.
```php
$user_ids = [542, 142, 443, 366, 888, 747, 636];
$ratings = [3.4, 5.0, 3.9, 4.3, 4.9, 3.8, 3.4];

// sort ratings in descending order
// sort user_ids in ascending order for equivalent values in the sorted ratings array
array_multisort($ratings, SORT_DESC, $user_ids, SORT_ASC);

var_dump($ratings);
var_dump($user_ids);

/*OUTPUT
    [5.0, 4.9, 4.3, 3.9, 3.8, 3.4, 3.4]
    [142, 888, 366, 443, 747. 542, 636]
*/
```

Hopefully the example makes things clearer.


Hmm. Not so bad is it? Why did I think this function is kind of messed up?

Well, it's mainly because there are other types of `sort_order` and `sort_flags` you can use for this function which would change/modify how it behaves. Not very [**S**OLID](https://scotch.io/bar-talk/s-o-l-i-d-the-first-five-principles-of-object-oriented-design) at all...

I'm not going to detail those other use cases anymore for this TIL. Just check the [`array_multisort doc`](http://php.net/manual/en/function.array-multisort.php)

Trudging on, sorting multi-dimensional arrays should be very similar. The common use case under this problem domain would be on sorting DB query results.

To cap things off, it is important to note that the arrays you pass into `array_multisort` must be of the same length! If it's a multi-dimensional array, the number of columns must also be the same!


