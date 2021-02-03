# Express Framework

Express is a popular structured web framework, written in JavaScript that runs on the node environment. js at run time. This module explains some of the main benefits of this framework, how to set up your development environment and how to perform common web development and deployment tasks.

### To install, type the following command

```bash
$ npm install express
```

Now, in your src/index.js JavaScript file, use the following code to import Express.js, to create an instance of an Express application, and to start it as Express server:

```
import express from 'express';
 
const app = express();
 
app.listen(3000, () =>
  console.log('Example app listening on port 3000!'),
);
```

Reference:

- https://developer.mozilla.org/pt-BR/docs/Learn/Server-side/Express_Nodejs

- https://www.robinwieruch.de/node-js-express-tutorial
