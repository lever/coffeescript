# lever/coffeescript

This is a fork from the final commit on `coffeescript` version 1 (8adb30bhttps://github.com/jashkenas/coffeescript/commit/8adb30b21203e5f361c93413a7b538886a6488dd).

The only change is to switch the in-process compiler (`node --require coffeescript/register`) to use the [`source-map-support`](https://www.npmjs.com/package/source-map-support) module for mapping stack traces back to the CoffeeScript source.

This enables correct stack trace line numbers when using the in-process CoffeeScript compiler alongside other in-process compilers that use `source-map-support`, like [`ts-node`](https://www.npmjs.com/package/ts-node) for TypeScript.

## CoffeeScript has moved!

CoffeeScript on NPM has moved to `coffeescript` (no hyphen). Please update references to `coffee-script` to use `coffeescript` instead.

Also, a new major version has been released under the `coffeescript` name. This new release targets modern JavaScript, with minimal breaking changes. Learn more at [http://coffeescript.org](http://coffeescript.org).
