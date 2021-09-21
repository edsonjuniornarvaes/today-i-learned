### 📌 Extension: ESLint

#### Configuring ESLint

To start, we must use the following command:

```console
yarn add eslint -D
```

And then we've already initialized it with:

```console
npx eslint --init
```

Now that we've started setting up ESLint, the first question concerns how we're going to use ESLint in our system:

```console
  To check syntax only
  To check syntax and find problems
▸ To check syntax, find problems, and enforce code style
```

Then choose what kind of modules the project uses, in the example I choose the first option _React_:

```console
? What type of modules does your project use? ...
▸ JavaScript modules (import/export)
  CommonJS (require/exports)
  None of these
```

In the next step, we select which framework we are using, in the example I will follow the previous step _React_:

```console
? Which framework does your project use? ...
▸ React
  Vue.js
  None of these
```

The next question is about TypeScript, in the example I won't use it, so I selected ** No **:

```console
? Does your project use TypeScript? » No / Yes
```

In the next step, we must select where our code will run:

```console
? Where does your code run? ...  (Press <space> to select, <a> to toggle all, <i> to invert selection)
√ Browser
  Node
```

Now we are asked to choose a style to be used in the project, we must choose between an existing one, create a style or use our own, I always choose to use an existing one and choose to use _AirBNB_:

```console
? How would you like to define a style for your project? ...
▸ Use a popular style guide
  Answer questions about your style
  Inspect your JavaScript file(s)
```

And finally, we chose the format of our configuration file, again a personal choice:

```console
? What format do you want your config file to be in? ...
▸ JavaScript
  YAML
  JSON
```

Once the settings are complete, ESLint will ask you if you want to install the dependencies using ** npm **, as our project is using ** yarn ** here you have two options:

- select ** Yes **, delete the `package.lock.json` file generated after installation and run` yarn` to install the dependencies into the ` yarn.lock` file
- select ** No **, copy the list of dependencies described and install them using `yarn add ...` (don't forget to add -D if you choose this option)

Now that we have our `.eslintrc` file, we assume the following settings for the configuration made above:

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: ["airbnb", "plugin:react/recommended"],
  parser: "babel-eslint",
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: "module",
  },
  plugins: ["react"],
  rules: {
    "react/jsx-filename-extension": ["warn", { extensions: [".js", ".jsx"] }],
    "import/prefer-default-export": "off",
    "jsx-quotes": ["error", "prefer-single"],
  },
};
```

[Install](https://eslint.org) the ESLint extension.
