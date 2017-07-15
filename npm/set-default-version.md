# Setting default node version using `nvm`

`nvm` is a handy version manager for nodejs.

To set a default version for each terminal session you have, you can simply do
```sh
nvm alias default <version>
```

However, for this to work, you must be sure that you have the version you wish to use as the default installed in your system.

To check this you can do
```sh
nvm ls
```

If you don't find the version, you can install it using `nvm`
```sh
nvm install <version>
```