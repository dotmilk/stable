## Stable [![Build Status](https://secure.travis-ci.org/Two-Screen/stable.png)](http://travis-ci.org/Two-Screen/stable)

A stable array sort, because `Array#sort()` is not guaranteed stable.

MIT licensed.

### From the browser

Include [`stable.js`] or the minified version [`stable.min.js`]
in your page, then call `stable()`.

 [`stable.js`]: https://raw.github.com/Two-Screen/stable/master/stable.js
 [`stable.min.js`]: https://raw.github.com/Two-Screen/stable/master/stable.min.js

### From Node.js

Install using NPM:

    npm install stable

Require in your code:

    var stable = require("stable");

#### Usage

The default sort is, as with `Array#sort`, lexicographical:

    stable(["foo", "bar"]);   // => ["bar", "foo"]
    stable([10, 1, 5]);       // => [1, 10, 5]

A comparator function can be specified:

    function cmp(a, b) { return a > b }
    var res = stable([10, 1, 5], cmp);  // -> [1, 5, 10]

Unlike `Array#sort`, sorting is **NOT** performed in-place.
