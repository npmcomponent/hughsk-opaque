*This repository is a mirror of the [component](http://component.io) module [hughsk/opaque](http://github.com/hughsk/opaque). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/hughsk-opaque`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# opaque #

Browserify module for detecting if an image or canvas element has transparent
pixels.

## Installation ##

Using [NPM](http://npmjs.org) and [Browserify](http://github.com/substack/node-browserify):

``` bash
npm install opaque
```

As a [component](http://github.com/component/component):

``` bash
component install hughsk/opaque
```

## Usage ##

`opaque(element)`

Returns `false` if transparent, or `true` if not.

`opaque.transparent(element)`

The opposite of `opaque`: `true` if transparent, `false` if not.

``` javascript
var opaque = require('opaque')
  , transparent = require('opaque').transparent

var brick = new Image
brick.src = '/brick.png'
brick.onload = function() {
  opaque(brick)      // true
  transparent(brick) // false
};

var glass = new Image
glass.src = '/glass.png'
glass.onload = function() {
  opaque(glass)      // false
  transparent(glass) // true
};
```

*Note that an image must be fully loaded before being checked.*
