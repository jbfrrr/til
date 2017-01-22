# Disk Usage `du` 

Basically `du` can recursively summarize for you the ff info below about files/directories for a given path:

* how much space they consume (_in multiple formats you can choose from_)
* when were they last modified

Below are some common examples on how to use it:

**use case 1**: List down the disk usage and last modified time (`--time`),  in human readable format(-`h`), of all files and directories (`-a`) directly under (`--max-depth=1 `) ~/Downloads. Include a grand total (`-c`) in the output.
```sh
du -hca --time --max-depth=1 ~/Downloads
```

**use case 2**: List down the disk usage and last modified time of all files, subdirectories/subfiles under `~/Downloads`. Output in human readable format and also add a grand total to the output.
```sh
du -hca --time ~/Downloads
```

**pro use case**: Get the top 3 largest consuming files/directories under `~/Downloads`
```
du -ha | sort -rh | head -4 #ignore the first entry in the output as it's just the size of `~/Downloads`
```

For more info/details about `du` check its manual by entering `man du` in your terminal.

