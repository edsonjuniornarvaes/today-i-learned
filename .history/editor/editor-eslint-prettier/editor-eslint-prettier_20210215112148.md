# ESLint + Prettier 

### Instalar
```bash
$ npm i - D eslint
```
### Instalar as dependências do Prettier formatter.
```bash
$ npm i -D prettier eslint-config-prettier eslint-plugin-prettier
```
### Crie um arquivo para a configuração do ESLint (.eslintrc.json) para adicionar as regras do Prettier.
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
###Configurar o VS Code para que  somente a extensão do ESLint formate o código.
```
{
  // habilitar o format on save (formatar ao salvar)
  "editor.formatOnSave": true,
  // configurar as ações que devem ser executadas ao salvar um arquivo
  "editor.codeActionsOnSave": {
    // executar o ESLint
    "source.fixAll.eslint": true
  },
  // desabilitar o plugin do Prettier para arquivos .js e .jsx
  "prettier.disableLanguages": ["javascript", "javascriptreact"]
}
```