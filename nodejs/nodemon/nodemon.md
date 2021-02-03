# Nodemon

According to the Nodemon website itself, this module is a utility that will monitor all changes to your application files and automatically restart the server when necessary. “Nodemon is a utility that will monitor for any changes in your source and automatically restart your server

### To install, type the following command

```bash
$ npm install -g nodemon
```
And to run your scripts, just run:
```bash
$ nodemon script.js
```

If you want, you can insert in the package.json file the scripts property with the configuration for defining the variable and pointing to the file in which you want to perform the monitoring.

```
{
 "scripts": {
    "dev": "nodemon index.js"
  }
}
```
with yarn installed, you can now run through the variable you defined in the pakage.json file, for example:

```bash
$ yarn dev
```

Reference:

- https://woliveiras.com.br/posts/Facilitando-o-desenvolvimento-Nodejs-com-Nodemon

- https://www.robinwieruch.de/node-js-express-tutorial
