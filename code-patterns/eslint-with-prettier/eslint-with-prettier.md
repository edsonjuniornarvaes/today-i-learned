##### 📌 Extension: ESLint

- The walkthrough below was reproduced in a next.js project

To start, we must use the following command:

```bash
yarn add eslint -D
```

And then we've already initialized it with:

```bash
npx eslint --init
```

Now that we've started setting up ESLint, the first question concerns how we're going to use ESLint in our system:

```bash
  To check syntax only
  To check syntax and find problems
▸ To check syntax, find problems, and enforce code style
```

Then choose what kind of modules our project uses, in this case how we are dealing with _React_ is the first option:

```bash
? What type of modules does your project use? ...
▸ JavaScript modules (import/export)
  CommonJS (require/exports)
  None of these
```

In the next step, we select which structure we are using, again, it will be the first option:

```bash
? Which framework does your project use? ...
▸ React
  Vue.js
  None of these
```

The next question is about TypeScript, since we are not configuring the project with it, just select
**No**:

```bash
? Does your project use TypeScript? » No / Yes
```

In the next step, we must select where our code will run:

```bash
? Where does your code run? ...  (Press <space> to select, <a> to toggle all, <i> to invert selection)
√ Browser
  Node
```

Now we are asked to choose a style to be used in the project, we must choose between an existing one, create a style or use our own, I always choose to use an existing one and choose to use _AirBNB_:

```bash
? How would you like to define a style for your project? ...
▸ Use a popular style guide
  Answer questions about your style
  Inspect your JavaScript file(s)
```

And finally, we chose the format of our configuration file, again a personal choice:

```bash
? What format do you want your config file to be in? ...
▸ JavaScript
  YAML
  JSON
```

Once the settings are complete, ESLint will ask you if you want to install the dependencies using ** npm **, as our project is using ** yarn ** here you have two options:

- select ** Yes **, delete the `package.lock.json` file generated after installation and run` yarn` to install the dependencies into the ` yarn.lock` file
- select ** No **, copy the list of dependencies described and install them using `yarn add ...` (don't forget to add -D if you choose this option)

Now that we have our `.eslintrc` file, we assume the following settings:

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: ['airbnb', 'plugin:react/recommended'],
  parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: 'module',
  },
  plugins: ['react'],
  rules: {
    'react/jsx-filename-extension': ['warn', { extensions: ['.js', '.jsx'] }],
    'import/prefer-default-export': 'off',
    'jsx-quotes': ['error', 'prefer-single'],
  },
};
```

[Install](https://eslint.org) the ESLint extension.

---

### 📌 Extension: [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

### Configuring Prettier

Here we will install two dependencies to configure _Prettier_ along with _ESLint_, the [first](https://github.com/prettier/eslint-config-prettier) disables the conflicting rules between _Prettier_ and _ESLint_ and the [second](https://github.com/prettier/eslint-plugin-prettier) transforms _Prettier_ and its settings into _ESLint_ rules, so we can integrate the two, come on:

```bash
yarn add -D prettier eslint-config-prettier eslint-plugin-prettier
```

Now let's update our `.eslintrc` file again, let's leave our `extends`, `plugins` and `rules` keys like this:

```js
extends: [
  "next",
  "next/core-web-vitals",
  "eslint:recommended",
  "prettier/react",
  "airbnb",
  "plugin:react/recommended",
  "plugin:prettier/recommended"
],
```

```js
plugins: ['react', 'prettier'],
rules: {
	'prettier/prettier':  'error',
}
```

Finally, create a `.prettierrc.json` file and configure it as follows:

```json
{
  "trailingComma": "es5",
  "tabWidth": 2,
  "semi": true,
  "singleQuote": true,
  "jsxSingleQuote": true
}
```

---
