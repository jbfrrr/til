# Downgrade package via `apt-get`

Sometimes the most updated version of a package just breaks things in your system...

To downgrade a package using `apt-get`, simply do:
```sh
sudo apt-get install <pkg-name>=<pkg-version>
```
or
```sh
sudo apt-get -t=<release> install <pkg-name>
```

To get all available versions of a package, do:
```sh
sudo apt-cache showpkg <pkg-name>
```

If you want to pin/hold a package at a specific version, thereby preventing auto updates, do:
```sh
sudo apt-mark hold <pkg-name>
```
