# file-extension
[![](https://img.shields.io/npm/v/file-extension.svg?style=flat)](https://www.npmjs.org/package/file-extension) [![](https://img.shields.io/npm/dm/file-extension.svg)](https://www.npmjs.org/package/file-extension) [![](https://api.travis-ci.org/silverwind/file-extension.svg?style=flat)](https://travis-ci.org/silverwind/file-extension)
> Get the extension of a given filename or path

Differences to [`path.extname`](https://nodejs.org/api/path.html#path_path_extname_path):

* Treats dotfiles as extension (`.eslintrc` => `eslintrc`)
* Doesn't include the dot in the extension (`package.json` => `json`).
* Returns lowercase by default (`Makefile` => `makefile`).

Works in Node.js and the browser. Currently the module size is **260 B bytes** gzipped.

## Installation
#### Node.js
```
$ npm install --save file-extension
```
#### Browser
```html
<script src="file-extension.js"></script>
<!-- Available as global `fileExtension` -->
```
## Example
```js
var fileExtension = require('file-extension'); // Skip this in the browser

// Case insensitive
fileExtension('file.zip');          //=> 'zip'
fileExtension('.Dockerfile');       //=> 'dockerfile'
fileExtension('file');              //=> 'file'
fileExtension('.file.tar');         //=> 'tar'

// Or with case preserved
fileExtension('.Vagrantfile', {preserveCase: true}); //=> 'Vagrantfile'
fileExtension('INDEX.HTML', {preserveCase: true});   //=> 'HTML'
```

## API
### fileExtension(filename, [options])
- `filename` {String} The file name. Required.
- `options` {Object} Options object.

#### Options
- `preserveCase` {Boolean} Whether case should be preserved. Default: false.

© [silverwind](https://github.com/silverwind), distributed under BSD licence
