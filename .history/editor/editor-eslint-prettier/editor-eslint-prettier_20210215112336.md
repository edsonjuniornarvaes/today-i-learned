# ESLint + Prettier 

### Install
```bash
$ npm i - D eslint
```
### Install the Prettier formatter dependencies.
```bash
$ npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```
### Create a file for the ESLint configuration (.eslintrc.json) to add the Prettier rules.
```
{
  "extends": ["prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": [
      "error",
      {
        "singleQuote": true
      }
    ]
  }
}
```
### Configure the VS Code so that only the ESLint extension formats the code.
```
{
  // enable format on save.
  "editor.formatOnSave": true,
  // configurar as ações que devem ser executadas ao salvar um arquivo.
  "editor.codeActionsOnSave": {
    // executar o ESLint
    "source.fixAll.eslint": true
  },
  // desabilitar o plugin do Prettier para arquivos .js e .jsx
  "prettier.disableLanguages": ["javascript", "javascriptreact"]
}
```