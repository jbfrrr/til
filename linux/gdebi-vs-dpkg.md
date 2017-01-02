# `gdebi` vs `dpkg`

 `gdebi` is a tool to install `.deb` files, much like `dpkg` but also resolves dependencies. This tool usually doesn't come with Linux out of the box but can be installed thru the terminal via apt:
 
 ```
 sudo apt-get install gdebi-core
 ```
 
If you don't want to use `gdebi`, you can resolve dependency issues after you install your chosen `.deb` package by running `sudo apt-get -f install`

**context**: I learned this today because I was trying to install and try a recommended markdown editor, [Remarkable](https://remarkableapp.github.io/linux.html) and came across depedency issues
