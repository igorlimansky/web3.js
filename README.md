# Migration 0.13.0 -> 0.14.0

web4.js version 0.14.0 supports [multiple instances of web4](https://github.com/ethereum/web4.js/issues/297) object.
To migrate to this version, please follow the guide:

```diff
-var web4 = require('web4');
+var Web3 = require('web4');
+var web4 = new Web3();
```


# Dapp RPC JavaScript API

[![Join the chat at https://gitter.im/ethereum/web4.js](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ethereum/web4.js?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

This is the Ethereum compatible [JavaScript API](https://github.com/ethereum/wiki/wiki/JavaScript-API)
which implements the [Generic JSON RPC](https://github.com/ethereum/wiki/wiki/JSON-RPC) spec. It's available on npm as a node module, for bower and component as an embeddable js and as a meteor.js package.

[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![dependency status][dep-image]][dep-url] [![dev dependency status][dep-dev-image]][dep-dev-url] [![Coverage Status][coveralls-image]][coveralls-url] [![Stories in Ready][waffle-image]][waffle-url]

<!-- [![browser support](https://ci.testling.com/ethereum/ethereum.js.png)](https://ci.testling.com/ethereum/ethereum.js) -->

You need to run a local RPC (Qtum or Eth) node to use this library.

[Documentation](https://github.com/ethereum/wiki/wiki/JavaScript-API)

## Installation

### Node.js

```bash
npm install web4
```

### Meteor.js

```bash
meteor add ethereum:web4
```

### As Browser module
Bower

```bash
bower install web4
```

Component

```bash
component install ethereum/web4.js
```

* Include `web4.min.js` in your html file. (not required for the meteor package)

## Usage
Use the `web4` object directly from global namespace:

```js
console.log(web4); // {eth: .., shh: ...} // it's here!
```

Set a provider (HttpProvider)

```js
web4.setProvider(new web4.providers.HttpProvider('http://localhost:8545'));
```

There you go, now you can use it:

```js
var coinbase = web4.eth.coinbase;
var balance = web4.eth.getBalance(coinbase);
```

You can find more examples in [`example`](https://github.com/ethereum/web4.js/tree/master/example) directory.


## Contribute!

### Requirements

* Node.js
* npm

```bash
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
sudo apt-get install nodejs-legacy
```

### Building (gulp)

```bash
npm run-script build
```


### Testing (mocha)

```bash
npm test
```

[npm-image]: https://badge.fury.io/js/web4.png
[npm-url]: https://npmjs.org/package/web4
[travis-image]: https://travis-ci.org/ethereum/web4.js.svg
[travis-url]: https://travis-ci.org/ethereum/web4.js
[dep-image]: https://david-dm.org/ethereum/web4.js.svg
[dep-url]: https://david-dm.org/ethereum/web4.js
[dep-dev-image]: https://david-dm.org/ethereum/web4.js/dev-status.svg
[dep-dev-url]: https://david-dm.org/ethereum/web4.js#info=devDependencies
[coveralls-image]: https://coveralls.io/repos/ethereum/web4.js/badge.svg?branch=master
[coveralls-url]: https://coveralls.io/r/ethereum/web4.js?branch=master
[waffle-image]: https://badge.waffle.io/ethereum/web4.js.svg?label=ready&title=Ready
[waffle-url]: https://waffle.io/ethereum/web4.js

