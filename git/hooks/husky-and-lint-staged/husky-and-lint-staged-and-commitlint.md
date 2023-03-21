![2](https://user-images.githubusercontent.com/42126267/226604074-9e39d4ac-9c17-4515-a1b9-2edfcf2de7e7.png)

In this post, I'll show you how to improve your husky workflow, using pre-commit to trigger error checking on your code before uploading it to the repository.

Start husky with the following command:
```sh
npx husky-init
```

Verify that the husky information has been entered into your package.json:
```json
{

  "scripts": {
    ...
    "prepare": "husky install"
  },
  "devDependencies": {
    ...
    "husky": "^6.0.0"
  }
}
```

Install husky in your project:
```sh
#yarn 
yarn; npx husky add .husky/commit-msg 'npx --no-install commitlint --edit ""'

#npm 
npm install; npx husky add .husky/commit-msg 'npx --no-install commitlint --edit ""'
```

Checking `.husky/commit-msg` file you might find the following bash script:
```sh
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

npx --no-install commitlint --edit ""
```

Let's add the commit-lint package to the lint confirmation messages:
```sh
#yarn 
yarn add @commitlint/config-conventional @commitlint/cli --dev

#npm 
npm install @commitlint/config-conventional @commitlint/cli --dev
```

Create the commitlint.config.js file in the root of your directory and insert the following contents:
```js
module.exports = { extends: ['@commitlint/config-conventional'] };
```

Now we will install lint-staged:
```sh
#yarn 
yarn add lint-staged --dev

#npm 
npm install lint-staged --save-dev
```

In package.json insert the following script for running lint-staged into our project:
```json
 {
   "scripts": {
     ...
     "pre-commit": "lint-staged",
     "prepare": "husky install"
   }
}
```

We will create the `.lintstagedrc` file to run eslint and prettier at commit time:
```js
{
  "src/**/*.+(js|json|ts|tsx)": ["eslint"],
  "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": ["eslint --fix", "prettier --write"]
}
```

Inside `.husky/pre-commit` insert the following script:
```sh
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

yarn run pre-commit
```

Finally, run the command that created the 'prepare-commit-msg' file:
```sh
#yarn
npx husky add .husky/prepare-commit-msg 'exec < /dev/tty && node_modules/.bin/cz --hook || true'; yarn

#npm
npx husky add .husky/prepare-commit-msg 'exec < /dev/tty && node_modules/.bin/cz --hook || true'; npm install
```

That's it! Now test everything we have installed.
