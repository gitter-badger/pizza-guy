# pizza-guy
[![Travis](https://img.shields.io/travis/andresdavid90/pizza-guy.svg?style=flat-square)](https://travis-ci.org/andresdavid90/pizza-guy)
[![Codecov](https://img.shields.io/codecov/c/github/andresdavid90/pizza-guy.svg?style=flat-square)](https://codecov.io/github/andresdavid90/pizza-guy)
[![NPM](https://img.shields.io/npm/v/pizza-guy.svg?style=flat-square)](https://www.npmjs.com/package/pizza-guy)
[![Downloads Total](https://img.shields.io/npm/dt/pizza-guy.svg?style=flat-square)](https://www.npmjs.com/package/pizza-guy)
[![Commitizen Friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)
[![Semantic Released](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)


If you already have a big list of urls of files that you want to download but you don't know how, this is your module.

The idea is to support really big lists of files that would be insane to download simultaneusly since Node would break for this kind of cases. Hope others to support this cause. ✌🏻

## How to use

### Require / Import

Using a transpiler like Babel:
```
import pizzaGuy from 'pizza-guy':
```
Use this syntax if you're not using a JS transpiler (see [here](https://medium.com/@kentcdodds/misunderstanding-es6-modules-upgrading-babel-tears-and-a-solution-ad2d5ab93ce0#.uk42faw0g) why):
```
const pizzaGuy = require('pizza-guy').default;
```
### Prepare your data
```
const images = [
  'http://some.domain.com/file0.jpg',
  'https://some.domain.com/file1.gif',
  'https://some.domain.com/file2.png'
];
```
### Execute
```
pizzaGuy
  // Pass an array of strings containing urls...
  .deliver(images)
  // Absolute or relative path to save these files...
  .onAddress('./some-path')
  // Will trigger per file...
  .onSuccess((info) => {
    console.log(`${info.fileName} succeed!`);
  })
  // Will trigger per file that failed..
  .onError((info) => {
    console.log(`${info.fileName} failed`);
  })
  // Initialize the utility!
  .start();
```

## Issues / bugs
We are working once on a while in this small library. Please report an issue [here](https://github.com/andresdavid90/pizza-guy/issues) and we'll take a look as soon as we can.
