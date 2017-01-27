# List installed packages

Knowing the installed packages in your system is a basic tool / life skill for responsible developers / administrators. Below are methods / commands for a couple of systems to get the information you need...

For Debian/Ubuntu:
```sh
sudo dpkg --get-selections
```

For RPM system:
```sh
yum list installed
```

For BSD systems:
```sh
pkg_version
```

**pro tip**: When you're backing up stuff or migrating, it's always good to save the list of installed packages of your system. Pipe the output to a file!