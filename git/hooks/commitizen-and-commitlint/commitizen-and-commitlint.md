### Configure and install Commitizen + Commitlint tools

---

What is Commitizen?

> [commitizen](http://commitizen.github.io/cz-cli/) will guide the developer through a commit. A string of options will be displayed to custom fill in any required fields during the commit.

What is Commitlint?

> [commitlint](https://commitlint.js.org/#/) will help you keep your commit within the conventions, will validate and indicate errors in your message.

Check the [commitment types](https://github.com/edsonjuniornarvaes/til/blob/master/git/hooks/husky-and-lint-staged/husky-and-lint-staged-and-commitlint.md)

Let's install two tools, they are commitlint/config-conventional and commitlint/cli, to install just insert the following command as a development dependency:

```bash
yarn add @commitlint/config-conventional @commitlint/cli -D
```

If necessary update the node, I leave a tutorial in the link below
[Updating the Node Version
](https://dev.to/edsonjuniornarvaes/updating-the-node-version-45j4)
Now let's create the commitlint.config.js file and add the config-conventional configuration

```js
module.exports = { extends: ["@commitlint/config-conventional"] };
```

Now that commitlint is ready to be used, we need to inform you that it needs to be executed after the commit request). For this we will integrate the husky ([configure husky + lint-staged](https://github.com/edsonjuniornarvaes/Til/blob/master/git/hooks/husky-and-lint-staged/husky-and-lint-staged.md)), the husky is a tool that allows us to create automated functionality based on git commands.

Before installing husky, we need to start git in our project so that the mapping between husky and git is done correctly:

```bash
git init
```

You can perform the installation of husky through this [article](https://github.com/edsonjuniornarvaes/til/blob/master/git/hooks/husky-and-lint-staged/husky-and-lint-staged-and-commitlint.md).

To test, just include a commit so that commitlint will already identify the message that does not follow Conventional Commits standards

```bash
git add .

git commit -m "initial commit"
```

If you followed the steps correctly, at this point an error will appear on the terminal with the details of the incorrect data. From now on you will follow Conventional standards, for example:

```bash
git commit -m "feat: add initial configuration"
```

We've finished setting up commit-lint. (Remembering that you can configure it however you like.)

Now let's configure and install commitizen

To install, let's enter the following command as development dependency

```bash
yarn add --dev commitizen cz-conventional-changelog
```

Now we need to configure the execution, we have two ways.

We can create a script in package.json

```json
"scripts": {
    "commit": "git-cz"
}
```

Will start the process of a new commit, to commit now just insert

```bash
git add .

yarn commit
```

From now on you will receive the following questions

> Select the type of commit, in the example I will select a feature

```txt
? Select the type of change you are making: talent: a new resource
```

> Now it will ask you what the scope is, if you want to define where you made the change

```txt
? What is the scope of this change (eg component or filename): (press Enter to skip)
```

> Here, it will ask you what the content of your commit is.

```txt
? Write a brief and imperative description of the change (max. 66 characters):
> (27) add commitizen configuration
```

> Now it will ask for a more complete description

```txt
? Provide a longer description of the change: (press Enter to skip)
> Sample message for description
```

To break a line, I can insert at the end of the line: \n\ nTest message

> Now it will ask if your commit removes something that worked and won't work anymore, some feature for example

```txt
? Are there any significant changes? (y/N) No
```

> Now you will be asked if the commit affects any issues that are open in our project? if so, it will ask what questions you want to close...

```txt
? Does this change affect any open issues? (y/N) No
```

Having followed the steps above, your commit will be completed

We can check the process we just did

```bash
git log
```
