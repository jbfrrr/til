# Disk Free `df`

Do you want to quickly know how much disk space you've got left for each filesystem in your machine? 

Simply use `df`! 

**sample**:  Display available space for all (`-a`) mounted filesystems on the machine in human readable format (`-h`)
```sh
> df -ha

# sample output
> 
Filesystem      Size  Used Avail Use% Mounted on
sysfs              0     0     0    - /sys
proc               0     0     0    - /proc
udev            3.9G  4.0K  3.9G   1% /dev
devpts             0     0     0    - /dev/pts
tmpfs           789M  1.2M  788M   1% /run
/dev/sda5        85G   44G   37G  55% /
none            4.0K     0  4.0K   0% /sys/fs/cgroup
none               0     0     0    - /sys/fs/fuse/connections
none               0     0     0    - /sys/kernel/debug
none               0     0     0    - /sys/kernel/security
none            5.0M     0  5.0M   0% /run/lock
none            3.9G  358M  3.5G  10% /run/shm
none            100M   24K  100M   1% /run/user
none               0     0     0    - /sys/fs/pstore
binfmt_misc        0     0     0    - /proc/sys/fs/binfmt_misc
systemd            0     0     0    - /sys/fs/cgroup/systemd
gvfsd-fuse         0     0     0    - /run/user/1000/gvfs
```

For more info, check the manual, `man df`
