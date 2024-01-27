# Alternative implementations

This is a list of packages we are aware of which have native equivalents or
lighter alternatives on NPM, along with any notes on migration.

Package | Alternative | Notes
--- | --- | ---
array-every | `Array.prototype.every` |
clone-regexp | `new RegExp(otherRegExp)` |
defaults | `Object.assign` or object spread (`{...obj}`) |
extend | `Object.assign` or object spread (`{...obj}`) | `extend` accepts a `deep` parameter which cannot be achieved by spread or assign, so may prevent migration
extend-shallow | `Object.assign` or object spread (`{...obj}`) |
filter-array | `Array.prototype.filter` |
has-own-prop | `Object.hasOwn` in modern engines, `Object.prototype.hasOwnProperty.call(obj, prop` otherwise |
index-of | `Array.prototype.indexOf` |
is-even | `(n % 2) === 0` |
is-nan | `Number.isNaN(obj)` |
is-npm | `process.env.npm_config_user_agent?.startsWith('npm')` |
is-number | `typeof obj === 'number'` |
is-odd | `(n % 2) === 1` |
is-regexp | `obj instanceof RegExp` or compare to `toString` result to `[object RegExp]` |
is-string | `typeof obj === 'string'` |
is-travis | `'TRAVIS' in process.env` |
is-whitespace | `str.trim() === ''` or a RegExp |
is-windows | `process.platform === 'win32'` |
last-index-of | `Array.prototype.lastIndexOf` |
left-pad | `String.prototype.padStart` |
pad-left | `String.prototype.padStart` |
q | `Promise` | Use native promises
qs | `URLSearchParams` | `URLSearchParams` is built in to the platform
query-string | `URLSearchParams` | `URLSearchParams` is built in to the platform
querystring | `URLSearchParams` | `URLSearchParams` is built in to the platform
querystringify | `URLSearchParams` | `URLSearchParams` is built in to the platform
xtend | `Object.assign` or object spread (`{...obj}`) |
