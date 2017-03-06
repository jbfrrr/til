# `pickle`

Here's the scenario.

You've just executed a script which does some deterministic yet expensive (resource and time intensive) operation to process some data into an object.

Say you run this script a couple of times every day via a cron job.

Notice, that having to do the heavy operation again and again only to come up with the same processed object is inefficient.

The efficient way to do it is to simply [**serialize**](https://en.wikipedia.org/wiki/Serialization) the result into a persistent file which you can load later on and just **deserialize** whenever you need the object.

And guess what, python's `pickle` library allows you to do just that!

Let's take a look at an example.

For context, let's say you want to do some machine learning magic and train your machine with some large preprocessed data set. To avoid having to do the preprocessing again and again, let's use `pickle`

```python
import pickle
import os.path

# import some kind module of yers that does
# the preprocessing and outputs the preprocessed data
from my_data_preprocessor import preprocess

file_name = 'preprocessed_data_file'

if (!os.path.exists("/home/user/" + file_name)):
    # store the preprocessed data
    preprocessed_data = preprocess()

    # open the file for writing
    file = open(file_name, 'wb')

    # this is where serialization happens
    pickle.dump(preprocessed_data, file)

    # close file
    file.close()

# open file for reading
file = open(file_name, 'r')

# deserialize the contents of the file to retrieve
# the preprocessed data in the form you expect
preprocessed_data = file.load()

# do other things with the data from here on...
```

So yeah, that's how pickling works basically.

In addition to `pickle`, python has another very similar library named `cpickle`. The main thing to remember here is that `cpickle` is implemented in C and the ff are its pros and cons:

`cpickle` Pros:

* It's way faster than `pickle`

`cpickle` Cons:

* `pickle` handles unicode objects while `cpickle` doesn't
* harder to debug since it's in C


<br>
Additional Resources:

* [What is Pickle in python?](https://pythontips.com/2013/08/02/what-is-pickle-in-python/)
* [Pickling in python](https://ianlondon.github.io/blog/pickling-basics/)
* [What's the purpose of serialization?](http://stackoverflow.com/questions/2232759/what-is-the-purpose-of-serialization-in-java)
