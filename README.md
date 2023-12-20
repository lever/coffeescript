# lever/coffeescript

This is a fork starting from the final commit on `coffeescript` version 1 [8adb30b](https://github.com/jashkenas/coffeescript/commit/8adb30b21203e5f361c93413a7b538886a6488dd).

Notable changes on top of the final v1 commit:

* Switch the in-process compiler (`node --require coffeescript/register`) to use the [`source-map-support`](https://www.npmjs.com/package/source-map-support) module for mapping stack traces back to the CoffeeScript source.
    - This enables correct stack trace line numbers when using the in-process CoffeeScript compiler alongside other in-process compilers that use `source-map-support`, like [`ts-node`](https://www.npmjs.com/package/ts-node) for TypeScript.
* Remove coffeescript/register's patch of `child_process.fork`
    - As of at least Node 8, it's no longer needed, and it causes an error `TypeError: Cannot set property 'filename' of undefined` when forking - see https://github.com/jashkenas/coffeescript/issues/4476
* Update class `extends` helper to also use prototype inheritance for static properties
    - This fixes an issue where a CoffeeScript class doesn't inherit static properties from ancestors of a class using static prototype inheritance.
    - For example, a CoffeeScript class would inherit static props directly declared a modern-ES or TS-transpiled class, but not any static props from a grandparent+ class.

To see all new commits:
https://github.com/jashkenas/coffeescript/compare/1...lever:coffeescript:coffee1-source-map-support

## CoffeeScript has moved!

CoffeeScript on NPM has moved to `coffeescript` (no hyphen). Please update references to `coffee-script` to use `coffeescript` instead.

Also, a new major version has been released under the `coffeescript` name. This new release targets modern JavaScript, with minimal breaking changes. Learn more at [http://coffeescript.org](http://coffeescript.org).
