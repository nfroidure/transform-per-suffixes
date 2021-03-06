<!--
# This file is automatically generated by a `metapak`
# module. Do not change it elsewhere, changes would
# be overridden.
-->
# transform-per-suffixes
> Map object properties according to suffixes.

[![NPM version](https://badge.fury.io/js/transform-per-suffixes.svg)](https://npmjs.org/package/transform-per-suffixes)
[![Build status](https://secure.travis-ci.org/nfroidure/transform-per-suffixes.svg)](https://travis-ci.org/nfroidure/transform-per-suffixes)
[![Dependency Status](https://david-dm.org/nfroidure/transform-per-suffixes.svg)](https://david-dm.org/nfroidure/transform-per-suffixes)
[![devDependency Status](https://david-dm.org/nfroidure/transform-per-suffixes/dev-status.svg)](https://david-dm.org/nfroidure/transform-per-suffixes#info=devDependencies)
[![Coverage Status](https://coveralls.io/repos/nfroidure/transform-per-suffixes/badge.svg?branch=master)](https://coveralls.io/r/nfroidure/transform-per-suffixes?branch=master)
[![Code Climate](https://codeclimate.com/github/nfroidure/transform-per-suffixes.svg)](https://codeclimate.com/github/nfroidure/transform-per-suffixes)
[![Dependency Status](https://dependencyci.com/github/nfroidure/transform-per-suffixes/badge)](https://dependencyci.com/github/nfroidure/transform-per-suffixes)

A simple helper to transform every properties of an object
 having a specific suffix.

I mainly use it to transform my JSONs according  to
 conventional prefixes. By example, for MongoDB
 ObjectIds.

# API
<a name="module_transform-per-suffixes"></a>

## transform-per-suffixes
<a name="module_transform-per-suffixes..transformPerSuffixes"></a>

### transform-per-suffixes~transformPerSuffixes(suffixes, val) ⇒ <code>Object</code> &#124; <code>Array</code>
Transform every properties of an object according to given suffixes.

**Kind**: inner method of <code>[transform-per-suffixes](#module_transform-per-suffixes)</code>  
**Returns**: <code>Object</code> &#124; <code>Array</code> - The modified object  

| Param | Type | Description |
| --- | --- | --- |
| suffixes | <code>Array</code> | An array of suffix definitions ({value: String, transform: Function}) |
| val | <code>Object</code> &#124; <code>Array</code> | The source Object/Array |

**Example**  
```js
var object = {
  _id: 'abbacacaabbacacaabbacaca',
  creation_date: '2015-11-28T16:22:47.552Z',
  value: 'Hey!'
};
var suffixes = [{
  value: '_id',
  transform: castToObjectId,
}, {
  value: '_date',
  transform: function(d) { return new Date(d) },
}];

console.log(transformPerSuffixes(suffixes, object));
// Prints:
// {
//   _id: ObjectId('abbacacaabbacacaabbacaca'),
//   creation_date: Date('2015-11-28T16:22:47.552Z'),
//   value: 'Hey!'
// }
```

# License
[MIT](https://github.com/nfroidure/transform-per-suffixes/blob/master/LICENSE)
