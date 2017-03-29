# `npm --save` and `npm --save-dev`

`npm` is a package manager we use to manage the `js` modules we need for whatever project it is we're working on that would require such modules so that other contributing developers won't need to worry about having to remember and manually install every dependency.

It is for this reason, that `npm` has a `package.json` containing the dependencies/modules your project needs. Ideally, all a new developer has to do is run `npm install` and things should be good.

_But what if we decided to add new dependencies? We can just do `npm install <some new dependency> ` right?_

Not so fast. Sure that would work on your end, but what about other developers?

_Gotcha. We can just manually update `package.json` right?_

Yeah, that's possible, but there's a more convenient way of doing things.

Enter `npm install --save <new dependency>` or `npm install --save-dev <new dependency>`.

**TL;DR** what the latter does is that it adds the new dependency in **devDependencies** part of your `package.json` which effectively installs only for development purposes. On the flip side, the former includes the dependency for public distribution (_e.g. for stuff that your project absolutely needs to function properly_).

For more info checkout:
- [`npm --save` or `--save-dev`. Which one to use?](http://imcodebased.com/npm-save-or-save-dev-which-one-to-use/)

