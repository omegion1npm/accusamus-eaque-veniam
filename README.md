# @omegion1npm/accusamus-eaque-veniam <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Given an object and a property, replaces a property descriptor (or deletes it), and returns a thunk to restore it.

## Example

```js
var mockProperty = require('@omegion1npm/accusamus-eaque-veniam');
var assert = require('assert');

var i = 0;
var object = {
	a: 1,
	get b() {
		i += 1;
		return 'b ' + i;
	}
};

assert.equal(object.a, 1);
assert.equal(object.b, 'b 1');
assert.equal(object.b, 'b 2');

var restoreA = mockProperty(object, 'a', { 'delete': true });
assert.equal('a' in object, false);

var restoreB = mockProperty(object, 'b', { value: 42 });
assert.equal(object.b, 42);

restoreA();
assert.equal('a' in object, true);

restoreB();
assert.equal(object.b, 'b 3');
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

## Security

Please email [@ljharb](https://github.com/ljharb) or see https://tidelift.com/security if you have a potential security vulnerability to report.

[package-url]: https://npmjs.org/package/@omegion1npm/accusamus-eaque-veniam
[npm-version-svg]: https://versionbadg.es/ljharb/@omegion1npm/accusamus-eaque-veniam.svg
[deps-svg]: https://david-dm.org/ljharb/@omegion1npm/accusamus-eaque-veniam.svg
[deps-url]: https://david-dm.org/ljharb/@omegion1npm/accusamus-eaque-veniam
[dev-deps-svg]: https://david-dm.org/ljharb/@omegion1npm/accusamus-eaque-veniam/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@omegion1npm/accusamus-eaque-veniam#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@omegion1npm/accusamus-eaque-veniam.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@omegion1npm/accusamus-eaque-veniam.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@omegion1npm/accusamus-eaque-veniam.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@omegion1npm/accusamus-eaque-veniam
[codecov-image]: https://codecov.io/gh/ljharb/@omegion1npm/accusamus-eaque-veniam/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@omegion1npm/accusamus-eaque-veniam/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@omegion1npm/accusamus-eaque-veniam
[actions-url]: https://github.com/omegion1npm/accusamus-eaque-veniam/actions
