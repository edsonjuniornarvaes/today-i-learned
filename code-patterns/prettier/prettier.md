### 📌 Configuring Prettier

Here we will install two dependencies to configure _Prettier_ together with _ESLint_, [(if you haven't installed ESLint, check the installation step by step)](https://github.com/edsonjuniornarvaes/til/tree/master/code-patterns/eslint/eslint.md) or [first](https : //github.com/prettier/eslint-config-prettier) disables conflicting rules between _Prettier_ and _ESLint_ and the [second] (https: //github.com/prettier/eslint-plugin-prettier) turns _Prettier_ and its settings into Rules _ESLint_, so we can integrate the two, let's go:

```console
yarn add -D prettier eslint-config-prettier eslint-plugin-prettier
```

Now let's update our `.eslintrc` file again, let's leave our keys` extends`, `plugins` and `rules`, in the example below I'll be configuring with react:

```js
extends: [
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
