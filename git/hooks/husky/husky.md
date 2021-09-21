In this post, I'll show you how to improve your husky workflow, using pre-commit to trigger error checking on your code before uploading it to the repository.

To get started, let's install husky with the following command:

```console
yarn add husky -D
```

In the package.json file I define the scope of the husky with the hook call and then the scope with the definition of the files to be checked, in the example I define the files that end in js and ts.

```json
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.{js, ts}": [""]
  }
```

At this point it is necessary to install and configure eslint, in this article I explain how to install eslint step by step [link]().

Here I configure it to automatically fix our changes: `eslint --fix`, if it can't fix the file, it will inform the user about the error, so I set git add to include the changes from` eslint -fix`

```json
  "lint-staged": {
      "*.{js, ts}": ["eslint --fix", "git add ."]
  }
```
