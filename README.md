# A starter for GDS Node.js projects

This repo is just the initial config for a Node.js project.

It uses [XO] to enforce code quality and formatting and [Husky], a module
that helps you run scripts on git hooks.

If you want to see [XO] in action, clone this repo and edit
`index.js` with some style errors e.g. use a `;` or indent badly. When
you run the commit `xo --fix` will remove the `;` and fix indentation.

Et voilà! Automagically keep your code consistent across the whole team.

## Adding to an existing project
To add this to an existing project, follow these three steps

1. Install the packages
```
npm install --save-dev xo husky lint-staged
```

2. Add the job that runs pre-commit
```json
{
  "lint-staged": {
    "*.js": [
      "xo --fix",
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

Next time you make a commit [Husky](https://github.com/typicode/husky) will kick in and [XO] will run.

👋

[XO]: https://github.com/sindresorhus/xo
[Husky]: https://github.com/typicode/husky
