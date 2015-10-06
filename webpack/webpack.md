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
### webpack - really simply
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
