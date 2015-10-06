title: Webpack
author:
	name: Gilad Goldberg
	twitter: giladgo
theme: sjaakvandenberg/cleaver-dark
controls: false
output: webpack.html
style: style.css
--
# webpack.js
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
# Demo 2
## Inline CSS
--
