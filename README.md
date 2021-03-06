Universal-Fetch
[![Build Status](https://travis-ci.org/pitzcarraldo/universal-fetch.svg?branch=master)](https://travis-ci.org/pitzcarraldo/universal-fetch)
[![npm version](https://img.shields.io/npm/v/universal-fetch.svg?style=flat-square)](https://www.npmjs.com/package/universal-fetch)
[![npm downloads](https://img.shields.io/npm/dm/universal-fetch.svg?style=flat-square)](https://www.npmjs.com/package/universal-fetch)
================

Fetch for node and browser (Webpack, Browserify) with IE8 support. Built on top of [GitHub's WHATWG Fetch polyfill](https://github.com/github/fetch).

## Warnings

- This adds `fetch` as a global so that its API is consistent between client and server.
- You must bring your own ES6 Promise compatible polyfill, I suggest [es6-promise](https://github.com/jakearchibald/es6-promise).

## Installation

### NPM

```sh
npm install --save universal-fetch es6-promise
```

### Bower

```sh
bower install --save universal-fetch es6-promise
```

## Usage

```js
require('es6-promise').polyfill();
require('universal-fetch');

fetch('//offline-news-api.herokuapp.com/stories')
	.then(function(response) {
		if (response.status >= 400) {
			throw new Error("Bad response from server");
		}
		return response.json();
	})
	.then(function(stories) {
		console.log(stories);
	});
```

## License

All open source code released by FT Labs is licenced under the MIT licence.  Based on [the fine work by](https://github.com/github/fetch/pull/31) **[jxck](https://github.com/Jxck)** and [isomorphic-fetch](https://github.com/matthew-andrews/isomorphic-fetch) .
