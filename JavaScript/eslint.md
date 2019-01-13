# ESLint

[Website](http://eslint.org) | [Configuring](http://eslint.org/docs/user-guide/configuring) | [Rules](http://eslint.org/docs/rules/) | [Contributing](http://eslint.org/docs/developer-guide/contributing) | [Twitter](https://twitter.com/geteslint) | [Mailing List](https://groups.google.com/group/eslint)

ESLint is a tool for identifying and reporting on patterns found in ECMAScript/JavaScript code. In many ways, it is similar to JSLint and JSHint with a few exceptions:

* ESLint uses [Espree](https://github.com/eslint/espree) for JavaScript parsing.
* ESLint uses an AST to evaluate patterns in code.
* ESLint is completely pluggable, every single rule is a plugin and you can add more at runtime.

## Installation

You can install ESLint using npm:

    npm install -g eslint

## Usage

    eslint test.js test2.js

### How does ESLint performance compare to JSHint?

ESLint is slower than JSHint, usually 2-3x slower on a single file. This is because ESLint uses Espree to construct an AST before it can evaluate your code whereas JSHint evaluates your code as it's being parsed. The speed is also based on the number of rules you enable; the more rules you enable, the slower the process.

Despite being slower, we believe that ESLint is fast enough to replace JSHint without causing significant pain.

### Is ESLint just linting or does it also check style?

ESLint does both traditional linting (looking for problematic patterns) and style checking (enforcement of conventions). You can use it for both.

### Where to ask for help?

Join our [Mailing List](https://groups.google.com/group/eslint)


[npm-image]: https://img.shields.io/npm/v/eslint.svg?style=flat-square
[npm-url]: https://npmjs.org/package/eslint
[travis-image]: https://img.shields.io/travis/eslint/eslint/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/eslint/eslint
[coveralls-image]: https://img.shields.io/coveralls/eslint/eslint/master.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/eslint/eslint?branch=master
[downloads-image]: http://img.shields.io/npm/dm/eslint.svg?style=flat-square
[downloads-url]: https://npmjs.org/package/eslint

The following is a sample .eslintrc

  {
      "env": {
          "node": true,
          "browser": true,
          "mocha": true,
          "es6": true
      },
      "ecmaFeatures": {
          "modules": true
      },
      "rules": {
          "no-alert": 2,
          "no-array-constructor": 2,
          "no-caller": 2,
          "no-bitwise": 2,
          "no-catch-shadow": 2,
          "no-console": 2,
          "no-comma-dangle": 2,
          "no-control-regex": 2,
          "no-debugger": 2,
          "no-div-regex": 2,
          "no-dupe-keys": 2,
          "no-else-return": 2,
          "no-empty": 2,
          "no-empty-class": 2,
          "no-eq-null": 2,
          "no-eval": 2,
          "no-ex-assign": 2,
          "no-extra-semi": 2,
          "no-func-assign": 2,
          "no-floating-decimal": 2,
          "no-implied-eval": 2,
          "no-with": 2,
          "no-fallthrough": 2,
          "no-unreachable": 2,
          "no-undef": 2,
          "no-undef-init": 2,
          "no-unused-expressions": 2,
          "no-octal": 2,
          "no-octal-escape": 2,
          "no-obj-calls": 2,
          "no-multi-str": 2,
          "no-new-wrappers": 2,
          "no-new": 2,
          "no-new-func": 2,
          "no-native-reassign": 2,
          "no-plusplus": 2,
          "no-delete-var": 2,
          "no-return-assign": 2,
          "no-new-object": 2,
          "no-label-var": 2,
          "no-ternary": 0,
          "no-self-compare": 2,
          "no-sync": 2,
          "no-underscore-dangle": 2,
          "no-loop-func": 2,
          "no-empty-label": 2,
          "no-unused-vars": 2,
          "no-script-url": 2,
          "no-proto": 2,
          "no-iterator": 2,
          "no-mixed-requires": [0, false],
          "no-wrap-func": 2,
          "no-shadow": 2,
          "no-use-before-define": 2,
          "no-redeclare": 2,
          "no-regex-spaces": 2,
          "brace-style": [2, "1tbs"],
          "block-scoped-var": 0,
          "camelcase": 2,
          "complexity": [0, 4],
          "curly": 2,
          "dot-notation": 2,
          "eqeqeq": 2,
          "global-strict": 0,
          "guard-for-in": 0,
          "max-depth": [0, 4],
          "max-len": [0, 80, 4],
          "max-params": [0, 3],
          "max-statements": [0, 10],
          "new-cap": 2,
          "new-parens": 2,
          "one-var": 2,
          "quotes": [2, "single"],
          "quote-props": 0,
          "radix": 0,
          "semi": 2,
          "space-after-keywords": [2, "always", { "checkFunctionKeyword": true } ],
          "space-before-blocks": [2, "always"],
          "strict": 2,
          "unnecessary-strict": 0,
          "use-isnan": 2,
          "valid-typeof": 0,
          "wrap-iife": 2,
          "wrap-regex": 0,
          "yoda": "always"
      }
  }
