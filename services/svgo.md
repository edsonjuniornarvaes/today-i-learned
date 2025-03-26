### How to optimize SVG files for better use in projects?

We often come across large and complex SVG files full of redundancies, which can be a hassle. Fortunately, we can optimize this with [SVGO](https://svgo.dev/), a tool that reduces the size of SVG files by removing unnecessary data without compromising quality.

How to use it?

To use it, install it globally with the following command:

```shell
# npm
npm install -g svgo

# yarn
yarn global add svgo

# pnpm
pnpm add -g svgo
```
Create an SVGO configuration file in the root of your project with the following command:

```shell
echo svgo.config.js
```
Open the svgo.config.js file and start configuring it. Below is an example, but feel free to explore other possibilities and even add plugins:

```js
module.exports = {
  multipass: false, /* Performs multiple passes over the file to try to find more possible optimizations.*/
  plugins: [
    { name: 
      'removeViewBox', active: false }, /* Keep the viewBox to avoid clipping. */
    { name: 'removeDimensions', active: true }, /* Remove width and height to allow scalability. */
  ]
};
```
Go to the location where the svg you want to optimize is located and run the following command:
```shell
svgo step_units.svg -o step_units.min.svg
```
That's it! Your svg is optimized, all the redundancies and unnecessary parameters that come with an svg have been removed and it is ready to use.

For more complete content, visit the [SVGO documentation](https://github.com/svg/svgo)
