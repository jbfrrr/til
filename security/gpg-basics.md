# `GPG` Basics

### What it is?
`GPG` aka GNU Privacy Guard is a program/software used to protect electronic communications, e.g. encrypting and decrypting messages, files or objects.

One simple use case of `GPG` would be a database admin sendng access credentials to a developer using the developer's public `GPG` key to encrypt the credentials before sending it across a secure network to the developer.

Another use case of `GPG` would be for signing stuff digitally e.g. signing your commits.

### `GPG` vs `PGP`?
TL;DR, `PGP`, aka Pretty Good Privacy serves the same purpose as `GPG`. However, `PGP` is **proprietary** software while `GPG` is **open source and free**. For more info about their differences:

- [Difference Between `PGP` and `GPG`](http://www.differencebetween.net/technology/software-technology/difference-between-pgp-and-gpg/)
- [Difference between `PGP` and `GPG`](http://askubuntu.com/questions/186805/difference-between-pgp-and-gpg)
- [OpenPGP, `PGP` and `GPG`: What is the difference?](https://www.goanywhere.com/blog/2013/07/18/openpgp-pgp-gpg-difference)
- [Are `GPG` and `PGP` compatible?](http://crypto.stackexchange.com/questions/13111/if-pgp-and-gpg-both-follow-the-openpgp-standard-are-they-100-compatible-in-all)

### How do I generate my `GPG` keys?
Github has neat guide for this! Check it out [here](https://help.github.com/articles/generating-a-new-gpg-key/)

### How do I publish my `GPG` keys?
1. Assuming you've already generated, first get your `GPG` public key id (long format):
```sh
gpg --list-public-keys --keyid-format LONG
```

2. Go to a public key server, e.g. [MIT PGP Public Key Server](https://pgp.mit.edu/) and submit your `GPG` key id in ASCII armor format, i.e. the value you get from the command below:
```sh
gpg --armor --export <step1_value>
```

3. After submission, test if you can retrieve your public key either by just plainly using the email you used to generate your keys or by using the long format of your key id corresponding to the email you used to generate your `GPG` key:
```sh
gpg -K --keyid-format 0xlong # get long format for your key ids
```

### Encrypting and Decrypting
```sh
# encrypt
gpg --encrypt --sign -r <receipient@email.com> <file_name>

# decrypt
gpg <file_name>
```

### Signing your commits?
[I've already made a TIL for that :)](../git/commit-signing.md)

### Still need more info?
- Check the manual via `man gpg`
- [Cheat Sheet](http://irtfweb.ifa.hawaii.edu/~lockhart/gpg/)
- [Tutorial](https://futureboy.us/pgp.html)
