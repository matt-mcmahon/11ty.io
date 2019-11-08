---
subtitle: Debugging
tags:
  - docs-getting-started
---
# Debugging

Having trouble? Want to see what Eleventy is doing behind the scenes? Use `DEBUG` mode. We’re taking advantage of the [excellent `debug` package](https://www.npmjs.com/package/debug) for this. Enable with the `DEBUG` env variable, either specific to eleventy (`DEBUG=Eleventy*`) or globally (`DEBUG=*`).

Either setting will have Eleventy tell you exactly what directories it's is using for data, includes, input, and output. It’ll tell you what search globs it uses to find your templates and what templates it finds. When you’re having trouble, `DEBUG`!

{% addedin "0.3.0" %} Works great with `--dryrun` if you want to run Eleventy but not actually write any files.


## Cross Platform Environment Variables

POSIX systems, like Mac and Linux, allow you to declare an environment variable assignment before a command:

```bash
DEBUG=Eleventy* npx eleventy
```

Windows, unfortunately, [does things differently](https://www.npmjs.com/package/debug#windows-command-prompt-notes). 
Using the package [`cross-env`](https://www.npmjs.com/package/cross-env), you can declare environment variables in a cross-platform comaptible way.
This command will work on Windows and POSIX; notice the call to `npx` now comes first:

```bash
npx cross-env DEBUG=Eleventy* eleventy
```

Learn more about the [`debug`](https://www.npmjs.com/package/debug) and [`cross-env`](https://www.npmjs.com/package/cross-env) packages by checking out their documentation.
