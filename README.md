# in-version

> Fancy git-tagging for npm modules.

This project provides a command line utility to create git tags of an npm
install-able version of your module.

The npm package manager allows you to install modules directly from a git
endpoint. This is great but can lead to larger package installs than necessary.
in-version creates tags that includes only those files which npm would grab
during a publish - usually whatever is listed in the [main attribute][npm-main]
of your package.json.


## Installation

You will typically want to install in-version globally:

```shell
npm install --global in-version
```

For pro points you can install in-version locally:

```shell
npm install --save-dev in-version
```


## Usage

Once installed, in-version makes the `inv` command available to you. This
command behaves a lot like [`npm version`][npm-version].

```shell
inv minor
```

After running the above:

- The minor version number in your package.json will be incremented (a la `npm
  version`)
- A publish-things-only tag will have been created (e.g. v1.1.0)
- The working copy will have been tagged as the corresponding dev version
  (e.g. v1.1.0-dev)

If in-version was installed locally you can either invoke it directly from
`./node_modules/.bin/inv` or create an npm script to run it.

For more information run `inv --help` or take a look at [usage.txt][usage].

## License

MIT

[npm-main]: https://docs.npmjs.com/files/package.json#main "npm main attribure"
[npm-version]: https://docs.npmjs.com/cli/version "npm version"
[usage]: blob/master/usage.txt "usage"
