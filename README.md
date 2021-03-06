balena-pine
----------

[![npm version](https://badge.fury.io/js/balena-pine.svg)](http://badge.fury.io/js/balena-pine)
[![dependencies](https://david-dm.org/balena-io-modules/balena-pine.png)](https://david-dm.org/balena-io-modules/balena-pine.png)
[![Circle Build Status](https://circleci.com/gh/balena-io-modules/balena-pine/tree/master.svg?style=shield)](https://circleci.com/gh/balena-io-modules/balena-pine)
[![Appveyor Build status](https://ci.appveyor.com/api/projects/status/8k6fb53ttm73m5ah/branch/master?svg=true)](https://ci.appveyor.com/project/resin-io/balena-pine/branch/master)

Join our online chat at [![Gitter chat](https://badges.gitter.im/balena-io/chat.png)](https://gitter.im/balena-io/chat)

Balena PineJS client.

Role
----

The intention of this module is to provide a ready to use subclass of [pinejs-client-js](https://github.com/balena-io/pinejs-client-js) which uses [balena-request](https://github.com/balena-io-modules/balena-request).

**THIS MODULE IS LOW LEVEL AND IS NOT MEANT TO BE USED BY END USERS DIRECTLY**.

Unless you know what you're doing, use the [balena SDK](https://github.com/balena-io/balena-sdk) instead.

Installation
------------

Install `balena-pine` by running:

```sh
$ npm install --save balena-pine
```

Documentation
-------------

Instantiate the PineJS like that:

```
const { BalenaPine } = require('balena-pine')
var pine = new BalenaPine({}, {
  apiUrl: "https://api.balena-cloud.com/",
  apiVersion: "v2",
  request: request, // An instantiated balena-request instance
  auth: auth // An instantiated balena-auth instance
})
```

Where the second argument of the constructor accepts the following options:
* `apiUrl`, string, **required**, is the balena API url like `https://api.balena-cloud.com/`,
* `apiVersion`, string, **required**, is the version of the API to talk to, like `v2`. The current stable version is `v2`,
* `apiKey`, string, *optional*, is the API key to make the requests with,
* `request`, object, an instantiated [balena-request](https://github.com/balena-io/balena-request) instance.
* `auth`, object, an instantiated [balena-auth](https://github.com/balena-io-modules/balena-auth) instance.



There are multiple builds you can use, to set the version globally use [@balena/es-version](https://github.com/balena-io-modules/balena-es-version), eg:
```js
// Must be set before the first require
require('@balena/es-version').set('es2015') // We support exact matches on es2015 (default) / es2018, see https://github.com/balena-io-modules/balena-es-version for a full list a possible versions
require('balena-pine') // requires the version set above
```
or to force a specific version overriding the default (not recommended) you can use
```js
require('balena-pine/es2015') // es2015/es6
require('balena-pine/es2018') // es2018
```


Head over to [pinejs-client-js](https://github.com/balena-io-modules/pinejs-client-js) for the returned PineJS instance documentation.

Support
-------

If you're having any problem, please [raise an issue](https://github.com/balena-io-modules/balena-pine/issues/new) on GitHub and the balena team will be happy to help.

Tests
-----

Run the test suite by doing:

```sh
$ npm test
```

Contribute
----------

- Issue Tracker: [github.com/balena-io-modules/balena-pine/issues](https://github.com/balena-io-modules/balena-pine/issues)
- Source Code: [github.com/balena-io-modules/balena-pine](https://github.com/balena-io-modules/balena-pine)

Before submitting a PR, please make sure that you include tests, and that [coffeelint](http://www.coffeelint.org/) runs without any warning:

```sh
$ npm run lint
```

License
-------

The project is licensed under the Apache 2.0 license.
