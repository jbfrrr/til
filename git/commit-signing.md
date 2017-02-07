# Signing commits

Want to make your commits extra **legit** ?

Sign them using your gpg key!

Prerequisite: [Generate a GPG Key](https://help.github.com/articles/generating-a-new-gpg-key/)

Configure git to use your key. Note that you may omit the `--global` setting if you want to do set this per-repository

```sh
git config --global user.signingkey <gpg key id>
```

You may then sign your commits by adding a `-S` e.g.:
```sh
git commit -S
```

_**fun fact**: I signed this particular TIL entry using my gpg key (`git log --show-signature`). See what I did ? LOLOLOL!_
