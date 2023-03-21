![2](https://user-images.githubusercontent.com/42126267/226604259-e1abcc22-88fe-4992-ac0a-ce9593110cc7.png)

<br>

In this post, I'll show you how to improve your husky workflow, using pre-commit to trigger error checking on your code before uploading it to the repository.

<br>

Start husky with the following command:
```sh
npx husky-init
```

<br>

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

<br>

Install husky in your project:
```sh
#yarn 
yarn; npx husky add .husky/commit-msg 'npx --no-install commitlint --edit ""'

#npm 
npm install; npx husky add .husky/commit-msg 'npx --no-install commitlint --edit ""'
```

<br>

Checking `.husky/commit-msg` file you might find the following bash script:
```sh
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

npx --no-install commitlint --edit ""
```

<br>

Let's add the commit-lint package to the lint confirmation messages:
```sh
#yarn 
yarn add @commitlint/config-conventional @commitlint/cli --dev

#npm 
npm install @commitlint/config-conventional @commitlint/cli --dev
```

<br>

Create the `commitlint.config.js` file in the root of your directory and insert the following contents:
```js
module.exports = { extends: ['@commitlint/config-conventional'] };
```

<br>

Now we will install lint-staged:
```sh
#yarn 
yarn add lint-staged --dev

#npm 
npm install lint-staged --save-dev
```

<br>

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

<br>

We will create the `.lintstagedrc` file to run eslint and prettier at commit time:
```js
{
  "src/**/*.+(js|json|ts|tsx)": ["eslint"],
  "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": ["eslint --fix", "prettier --write"]
}
```

<br>

Inside `.husky/pre-commit` insert the following script:
```sh
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

yarn run pre-commit
```
<br>

Finally, run the command that created the 'prepare-commit-msg' file:
```sh
#yarn
npx husky add .husky/prepare-commit-msg 'exec < /dev/tty && node_modules/.bin/cz --hook || true'; yarn

#npm
npx husky add .husky/prepare-commit-msg 'exec < /dev/tty && node_modules/.bin/cz --hook || true'; npm install
```
<br>

That's it! Now test everything we have installed.
