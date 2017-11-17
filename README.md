# A starter for GDS Node.js projects

This repo is just the initial config for a Node.js project.

It uses [XO] to enforce code quality and [Prettier] for code formatting.

[Husky] is a module that helps you run scripts on git hooks.

The scripting within `package.json` was inspired by the [Prettier docs](https://prettier.io/docs/en/precommit.html)
and [Zeit’s implementation](https://github.com/zeit/now-desktop/issues/266).

If you want to see XO and prettier in action, clone this repo and edit
`index.js` with some style errors e.g. use a `var` or indent badly. When
you run the commit `xo --fix` will change this to a `const` (or a `let` in
the right circumstances).

Et voilà! Automagically keep your code consistent across the whole team.

👋

[XO]: https://github.com/sindresorhus/xo#editor-plugins
[Prettier]: https://prettier.io
[Husky]: https://github.com/typicode/husky
