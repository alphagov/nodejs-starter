# A starter for GDS Node.js projects

This repo is just the initial config for a Node.js project.

It uses [xo] to enforce code quality and [Prettier] for code formatting.

[Husky] is a module that helps you run scripts on git hooks.

The scripting within `package.json` was inspired by the [Prettier docs](https://prettier.io/docs/en/precommit.html)
and [Zeit’s implementation](https://github.com/zeit/now-desktop/issues/266).

If you want to see xo and prettier in action, clone this repo and edit
`index.js` with some style errors e.g. use a `var` or indent badly. When
you run the commit `xo --fix` will change this to a `const` (or a `let` in
the right circumstances).

Et voilà! Automagically keep your code consistent across the whole team.

## Adding to an existing project
To add this to an existing project, follow these four instructions

1. Install the packages
```
npm install --save-dev xo prettier eslint-config-prettier husky lint-staged
```

2. Configure xo to use prettier by adding this to your `package.json` (xo accepts [a lot more config](https://github.com/sindresorhus/xo#config) too)
```json
{
  "xo": {
    "extends": [
      "prettier"
    ],
    "ignore": [
      "node_modules/**/*.*"
    ]
  },
}
```

3. Add the job that runs pre-commit
```json
{
  "lint-staged": {
    "*.js": [
      "xo --fix",
      "npm run lint",
      "prettier --write",
      "git add"
    ],
    "*.scss": [
      "prettier --write",
      "git add"
    ]
  },
}
```

4. Register the pre-commit job in scripts
```json
{
  "scripts":{
    "precommit": "lint-staged"
  }
}
```

Next time you make a commit [Husky](https://github.com/typicode/husky) will kick in and [xo] will run.

👋

[xo]: https://github.com/sindresorhus/xo#editor-plugins
[Prettier]: https://prettier.io
[Husky]: https://github.com/typicode/husky
