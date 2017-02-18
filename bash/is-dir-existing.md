# Is `dir` existing?

To check if a directory `dir` is existing in bash, simply do something like:
```sh
if [ -d /home/user1/mydocs/ ]
then
    echo '/home/user1/mydocs/ exists';
else
    echo '/home/user1/mydocs/ does not exist';
fi
```

Optionally, you can put the directory in question in a variable and do something like:
```sh
dir=/home/user1/mydocs/
if [ -d "$dir" ]; then echo "$dir exists"; else "$dir does not exist'; fi
```

Futhermore, you can support checking for symbolic links to directories e.g.:
```sh
dir=/home/user1/mydocs/
if [ -d "$dir" ]
then
    if [ -L "$dir" ]
    then
        echo "Symlink $dir exists";
    else
        echo "Directory $dir exists";
    fi
else
    echo "Directory $dir not found.";
fi
```
