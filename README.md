# vax

## Description

Check a local node module for npm security best practices. Currently, it simply:

1. Checks if you have an `.npmrc` file with `save-exact=true` in it.
1. Checks if an `npm-shrinkwrap.json` file is present.
1. Checks your `package.json` for any loose range specifiers (~, ^, <, >).

It will do its best to fix these problems for you.

## Usage

```
npm install -g vax
```

And then run `vax` with the location of your node module.

```
vax ~/Projects/my-node-project

> error: No .npmrc file found. Please create one and add `save-exact=true` to it.
> error: Please shrinkwrap your dependencies by running `npm shrinkwrap`.
> info: Your `package.json` file looks good.
```

To automatically fix any problems, use the `--fix` option.

```
vax ~/Projects/my-node-project

> info: No .npmrc file found. I created one for you.
> info: Your `package.json` file looks good.
> info: I reinstalled and shrinkwrapped your dependencies for you.
```

## License

Copyright (c) 2016 Chris Contolini

[MIT License](http://en.wikipedia.org/wiki/MIT_License)
