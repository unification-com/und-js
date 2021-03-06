[![npm version](http://img.shields.io/npm/v/@unification-com/und-js.svg?style=flat)](https://npmjs.org/package/@unification-com/und-js "View this project on npm")


# UND Mainchain JavaScript SDK

The UND Mainchain JavaScript SDK allows browsers and node.js clients to 
interact with UND Mainchain. It includes the following core components:

* **crypto** - core cryptographic functions.
* **client** - implementations of UND Mainchain transaction types, 
such as for transfers and enterprise and REST queries.
* **accounts** - management of "accounts" and wallets, including seed and encrypted mnemonic generation.

# Installation

Important, please follow the instructions for your OS below:

**Windows users:** Please install [windows-build-tools](https://www.npmjs.com/package/windows-build-tools) first.

**Mac users:** Make sure XCode Command Line Tools are installed: `xcode-select --install`.

**Linux users:** Note that Ubuntu Xenial and newer distributions are 
recommended, especially when using Travis or other CI systems. You may
 need some dev packages to be installed on your system for USB support. 
 On Debian-based distributions (like Ubuntu) you should install them 
 with this command:
 
```bash
$ sudo apt-get install libudev-dev libusb-dev usbutils
```

### Install the NPM package

```bash
$ npm i @unification-com/und-js --no-optional
```

# API

For up-to-date API documentation, please check the 
[API Docs](https://github.com/unification-com/und-js/blob/master/docs/jsdoc.md).

# Testing

Tests are currently run against the
[UND Mainchain DevNet](https://github.com/unification-com/mainchain/blob/master/docs/local-devnet.md)

All new code changes should be covered with unit tests. 
You can run the tests with the following command:

```bash
$ npm run test
```

# Contributing

Contributions to the UND Mainchain JavaScript SDK are welcome. Please 
ensure that you have tested the changes with a local client and have 
added unit test coverage for your code.
