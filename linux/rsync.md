# `rsync`

... `wip`

TL;DR `rsync` is a program in linux that helps us send/copy over files across the network between different machines.

... `wip`

#### Excluding files or directories
Option 1: Just add `--excludes='<dir|file>'` for every directory or file you wish for rsync to exclude syncing to another machine.

```sh
# excludes build files
rsync /home/personal/code/ $username@$remote_ip:~/code -auvz --exclude='build'
```

Option 2: Use an exclusion file and add `--exclude-from '<exclusion_file>'` to your rsync config. This is especially useful if you have a lot of files or directories to exclude.

```sh
# exclude all file paths in exclusion_file.txt
rsync /home/personal/code/ $username@$remote_ip:~/code -auvz --exclude-from ''exclusion_file.txt'
```

#### Resources:
- [`rsync` examples](http://www.thegeekstuff.com/2011/01/rsync-exclude-files-and-folders/?utm_source=feedburner)

