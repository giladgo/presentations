title: Webpack
author:
	name: Gilad Goldberg
	twitter: giladgo
theme: sjaakvandenberg/cleaver-dark
controls: false
output: webpack.html
style: style.css
--
# webpack
## module bundler
## http://webpack.github.io/
--
# browserify?
--
# browserify?
* webpack is kind of like browserify on steroids
* can do pretty much everything that browserify does and more
* build system
--
### webpack - the basics
* `a.js` which has:
  ```javascript
  require('b.js');
  require('c.js');
  ```
* `b.js` which has:
  ```javascript
  require('c.js');
  require('d.js');
  ```
* webpack will compile it into `app.js`, which contains all of the above code, without repeats, and can be loaded in the browser (or anything, really).
-- what-is
![](http://webpack.github.io/assets/what-is-webpack.png)
--
# Demo 1
## Basic webpack (from the tutorial)
--
### `require`ing things that aren't JS
* You can also `require()` other things like CSS files, .jade/.dust templates.
  * So you'd write
  	```javascript
  	require("!style!css!./style.css");
	```
* It all depends on if you have the appropriate **loader**.
  * ```
	$ npm install css-loader style-loader
	```
  * `css-loader` is responsible for loading css files on `require()`.
  * `style-loader` is responsible for appending the `<style>` tag to the doc.
--
### `webpack.config.js`
Instead of writing the options in the command line, we would use a config file, which is normally called `webpack.config.js`.
```javascript
module.exports = {
    entry: "./entry.js",
    output: {
        path: __dirname,
        filename: "bundle.js"
    },
    module: {
        loaders: [
            { test: /\.css$/, loader: "style!css" }
        ]
    }
};
```
This allows us to use automatic loaders, so we don't have to write the `!..!..`
--
# Demo 2
## Inline CSS
--
### MOAR LOADERS
```javascript
loaders: [
    { test: /\.css$/, loader: "style!css" },
	{ test: /\.coffee$/, loader: "coffee" },
	{ test: /\.jade$/, loader: "jade" }
]
```
--
### Development server
```
$ npm install webpack-dev-server -g
$ webpack-dev-server --progress --colors
```
* Runs in "watch mode"
  * checks for changes in the background and re-runs the process each time a file changes.
* Creates a server (port 8080, but configurable) which serves the files statically.
--
# Demo 3
## `webpack-dev-server`
--
# Demo 4
## webpack & PayPal.Me
--
### More features
* Supports AMD **and** CommonJS (and ES6 modules)
* Shimming
* Supports code splitting
  * Allows to split your code into chunks.
  * Great for having a chunck per page.
  * Didn't try; don't know.
--
# Q & A
--
# `/giphy the end`
## src is at https://github.com/giladgo/presentations/tree/master/webpack
