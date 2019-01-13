# Karma Mocha Chai

Project source: [https://github.com/zpratt/karma-mocha-chai](https://github.com/zpratt/karma-mocha-chai)
Source: [http://attackofzach.com/setting-up-a-project-using-karma-with-mocha-and-chai/](http://attackofzach.com/setting-up-a-project-using-karma-with-mocha-and-chai/)

# Karma

**Karma is only good for testing browser-based code**

Recently, I was on a quest to evaluate the [mocha](http://visionmedia.github.io/mocha/) javascript testing framework
and its direct support for async testing in the browser. I had a hard time finding a complete description of everything that needed to be done in order to get things working with karma for testing in the browser as opposed to testing a node module.

Consequently, I decided it would be useful to create a guide for those who have similar interests to save everyone time. If you want to skip the steps and just download the code, feel free to clone my [github repository](https://github.com/zpratt/karma-mocha-chai). As a quick aside, I decided to try mocha thanks to some frustrations with jasmine. Async testing with jasmine can be done, but it does not have first-class support in my opinion. I intend to give [http://docs.busterjs.org/en/latest/](http://docs.busterjs.org/en/latest/) a spin in the near future as well.

This tutorial assumes that you are on a unix-based system (I used OSX to write the article) and already have a working nodejs and npm installation, therefore installing and configuring a node.js/npm environment is outside the scope of this article. With that said, let's dig in!

1. Create a directory to hold the project and navigate to that directory:
  * `mkdir <new_dir>`
  * `cd <new_dir>`
2. We'll be installing a bunch of npm modules, so let's run `npm init` to build our package.json file for us
3. Let's install [karma](http://karma-runner.github.io/) with npm. I recommend installing it locally, since it's likely that you'll be either executing karma from an IDE (such as webstorm) or as a grunt task. Additionally, one project may be configured for one version of karma while a different project can use a different version if needed.
  * `npm install karma --save-dev`
  * At the time I wrote this article, the latest stable version of karma was 0.10.8.
4. Now we're ready to install mocha:
  * `npm install mocha --save-dev`
5. We'll also need the karma-mocha adapter so we can use mocha as a test framework with karma:
  * `npm install karma-mocha --save-dev`
6. An assertion library will need to included as well. I prefer the [chai assertion library](http://chaijs.com/), since it offers both bdd style assertions using expect and should as well as junit-style assertions.
  * `npm install karma-chai --save-dev`.
  * Installing chai this way will make it available as a framework within karma, which makes setup much simpler.
7. I also find [sinon](http://sinonjs.org/) to be extremely useful for stubbing and spying, so let's install it to round out our set of packages required to get our test environment provisioned:
  * `npm install karma-sinon --save-dev`

At this point, our package.json should have a devDependencies directive that looks something like this:

**devDependencies**: <script src="https://gist.github.com/zpratt/c2d872b329b48455c668.js"></script>

We can now create our karma configuration and write some tests. Let's first make sure that our karma installation is working correctly:

  * `./node_modules/karma/bin/karma --version`

That should print out the version number to the console if everything is working correctly. If you want to, you can initialize a karma configuration file using:

  * `./node_modules/karma/bin/karma init`

I'll provide the boilerplate so you can avoid that step. Include the following configuration in a file named

**karma.conf.js**: <script src="https://gist.github.com/zpratt/0ce8c9226529c5dbb137.js"></script>

Once that file is ready, we can create a failing test to ensure our configuration is working as expected. Create a new file in src/test called **test.spec.js**. Create the directory:

  * `mkdir -p src/test`

And a test file with the following contents:

  <pre>
  describe("A test suite", function() {
     beforeEach(function() { });
     afterEach(function() { });
     it('should fail', function() { expect(true).to.be.false; });
  });
  </pre>

With our test spec in place, we can run karma and make sure that we can successfully execute failing tests. `./node_modules/karma/bin/karma start karma.conf.js`

After running our tests, we should see some output along the lines of

  <pre>A test suite should fail FAILED</pre>

If so, then you've successfully configured karma with mocha, chai and sinon. Cheers!

## Project files

This following is the `Gruntfile.js`, as indicated it will identify the karma configuration file `karma.conf.js`

  module.exports = function (grunt) {
      grunt.initConfig({
          pkg: grunt.file.readJSON('package.json'),
          eslint: {
              target: ['./Gruntfile.js', 'test/*.spec.js', 'src/**/*.js']
          },
          karma: {
              unit: {
                  configFile: 'karma.conf.js',
                  singleRun: true,
                  reporters: 'progress',
                  runnerPort: 9998
              }
          }
      });

      require('load-grunt-tasks')(grunt);

      grunt.registerTask('default', ['eslint', 'karma']);
  };

This is the `karma.config.js`

  module.exports = function (config) {
      'use strict';
      config.set({

          basePath: '',

          frameworks: ['mocha', 'chai'],

          files: [
              'src/*.js',
              'test/*.spec.js'
          ],

          reporters: ['progress'],

          port: 9876,
          colors: true,
          autoWatch: false,
          singleRun: false,

          // level of logging
          // possible values: config.LOG_DISABLE || config.LOG_ERROR || config.LOG_WARN || config.LOG_INFO || config.LOG_DEBUG
          logLevel: config.LOG_INFO,

          browsers: ['PhantomJS']

      });
  };

This file identifies the `mocha` and `chai` as the testing framework.
the testing environement is the `src` and `test`
in the `test` directory the file test.spec.js` exists. The following is the content of this file:

    describe('A test suite', function () {
        var expect = window.expect;
        beforeEach(function () {
        });
        afterEach(function () {
        });
        it('should fail', function () {
            expect(true).to.be.equal(false);
        });
    });

# Mocha and Chai

source:

* [https://hackernoon.com/how-to-run-mocha-chai-unit-tests-on-node-js-apps-832eb2eba590](https://hackernoon.com/how-to-run-mocha-chai-unit-tests-on-node-js-apps-832eb2eba590)

## How to run Mocha/Chai unit tests on Node.js apps

We’ll start with creating a simple Node.js application, just like we usually do. The subsequent part of this article will explain how to write, run, and automate tests with BuddyWorks.

### Install NPM and Mocha
Create a directory for the application:

  mkdir myapp && cd myapp

Now, npm should be initialized. We’ll use it in order to create a package.json with the Mocha framework:

  npm init

You will be asked for the application’s details. Type the following:

  name: hello-world
  entry point: app.js
  test command: ./node_modules/.bin/mocha This framework will be used for testing the application
  Confirm the rest of the values by hitting enter.

### Create Hello World with Express framework

Express Node.js web application framework will be used for building the app:

  npm install express --save

### Details of Hello World

Once you already have everything installed, let’s create an app.js file with a simple HTTP server that will serve our Hello World website:
  //Load express module with `require` directive
  var express = require('express')
  var app = express()
  //Define request response in root URL (/)
  app.get('/', function (req, res) {
    res.send('Hello World')
  })
  //Launch listening server on port 8080
  app.listen(8080, function () {
    console.log('App listening on port 8080!')
  })

### Run the app
Now, the application is ready to launch:

  $ node app.js

Go to: http://localhost:8080/ in your browser to view it.

### Configuring unit tests with Mocha and Chai

Each single application should be tested before the deployment to the server, especially, if it’s a welcome site that creates the first
impression. Here, we will use Mocha as the test running framework, and Chai as the assertion library.

Install Mocha and Chai

Make sure to add Mocha and Chai packages to the package.json:

  npm install mocha --save
  npm install chai --save

## See also

* [http://mherman.org/blog/2016/09/12/testing-node-and-express/#.WbBGEmtSyou](http://mherman.org/blog/2016/09/12/testing-node-and-express/#.WbBGEmtSyou)
* [https://github.com/mjhea0/express-testing-mocha-knex](https://github.com/mjhea0/express-testing-mocha-knex) code for the above article.
* [http://mherman.org/blog/2017/05/11/developing-microservices-node-react-docker/#.WbBGaGtSyos](http://mherman.org/blog/2017/05/11/developing-microservices-node-react-docker/#.WbBGaGtSyos)
* [http://mherman.org/blog/categories/node/](http://mherman.org/blog/categories/node/) good list of articles

# ChaiJS

<h1 align=center>
  <a href="http://chaijs.com" title="Chai Documentation">
    <img alt="ChaiJS" src="http://chaijs.com/img/chai-logo.png">
  </a>
  <br>
  chai
</h1>

<p align=center>
  Chai is a BDD / TDD assertion library for <a href="http://nodejs.org">node</a> and the browser that can be delightfully paired with any javascript testing framework.
</p>

<p align=center>
  <a href="./LICENSE">
    <img
      alt="license:mit"
      src="https://img.shields.io/badge/license-mit-green.svg?style=flat-square"
    />
  </a>
  <a href="https://github.com/chaijs/chai/releases">
    <img
      alt="tag:?"
      src="https://img.shields.io/github/tag/chaijs/chai.svg?style=flat-square"
    />
  </a>
  <a href="https://www.npmjs.com/packages/chai">
    <img
      alt="node:?"
      src="https://img.shields.io/badge/node-%3E=4.0-blue.svg?style=flat-square"
    />
  </a>
  <br/>
  <a href="https://saucelabs.com/u/chaijs">
    <img
      alt="Selenium Test Status"
      src="https://saucelabs.com/browser-matrix/chaijs.svg"
    />
  </a>
  <br/>
  <a href="https://www.npmjs.com/packages/chai">
    <img
      alt="downloads:?"
      src="https://img.shields.io/npm/dm/chai.svg?style=flat-square"
    />
  </a>
  <a href="https://travis-ci.org/chaijs/chai">
    <img
      alt="build:?"
      src="https://img.shields.io/travis/chaijs/chai/master.svg?style=flat-square"
    />
  </a>
  <a href="https://coveralls.io/r/chaijs/chai">
    <img
      alt="coverage:?"
      src="https://img.shields.io/coveralls/chaijs/chai/master.svg?style=flat-square"
    />
  </a>
  <a href="">
    <img
      alt="devDependencies:?"
      src="https://img.shields.io/david/chaijs/chai.svg?style=flat-square"
    />
  </a>
  <br/>
  <a href="https://chai-slack.herokuapp.com/">
    <img
      alt="Join the Slack chat"
      src="https://img.shields.io/badge/slack-join%20chat-E2206F.svg?style=flat-square"
    />
  </a>
  <a href="https://gitter.im/chaijs/chai">
    <img
      alt="Join the Gitter chat"
      src="https://img.shields.io/badge/gitter-join%20chat-D0104D.svg?style=flat-square"
    />
  </a>
  <a href="https://opencollective.com/chaijs">
    <img
      alt="OpenCollective Backers"
      src="https://opencollective.com/chaijs/backers/badge.svg?style=flat-square"
    />
  </a>
</p>

For more information or to download plugins, view the [documentation](http://chaijs.com).

## What is Chai?

Chai is an _assertion library_, similar to Node's build in `assert`. It makes testing much easier by giving you lots of assertions you can run against your code.

## Installation

### Node.js

`chai` is available on [npm](http://npmjs.org). To install it, type:

    $ npm install chai

### Browsers

You can also use it within the browser; install via npm and use the `chai.js` file found within the download. For example:

```html
<script src="./node_modules/chai/chai.js"></script>
```

## Usage

Import the library in your code, and then pick one of the styles you'd like to use - either `assert`, `expect` or `should`:

```js
var chai = require('chai');  
var assert = chai.assert;    // Using Assert style
var expect = chai.expect;    // Using Expect style
var should = chai.should();  // Using Should style
```

### Pre-Native Modules Usage (_registers the chai testing style globally_)

```js
require('chai/register-assert');  // Using Assert style
require('chai/register-expect');  // Using Expect style
require('chai/register-should');  // Using Should style
```

### Pre-Native Modules Usage (_as local variables_)

```js
const { assert } = require('chai');  // Using Assert style
const { expect } = require('chai');  // Using Expect style
const { should } = require('chai');  // Using Should style
should();  // Modifies `Object.prototype`

const { expect, use } = require('chai');  // Creates local variables `expect` and `use`; useful for plugin use
```

### Native Modules Usage (_registers the chai testing style globally_)

```js
import 'chai/register-assert';  // Using Assert style
import 'chai/register-expect';  // Using Expect style
import 'chai/register-should';  // Using Should style
```

### Native Modules Usage (_local import only_)

```js
import { assert } from 'chai';  // Using Assert style
import { expect } from 'chai';  // Using Expect style
import { should } from 'chai';  // Using Should style
should();  // Modifies `Object.prototype`
```

### Usage with Mocha

```bash
mocha spec.js -r chai/register-assert  # Using Assert style
mocha spec.js -r chai/register-expect  # Using Expect style
mocha spec.js -r chai/register-should  # Using Should style
```

[Read more about these styles in our docs](http://chaijs.com/guide/styles/).

## Plugins

Chai offers a robust Plugin architecture for extending Chai's assertions and interfaces.

- Need a plugin? View the [official plugin list](http://chaijs.com/plugins).
- Want to build a plugin? Read the [plugin api documentation](http://chaijs.com/guide/plugins/).
- Have a plugin and want it listed? Simply add the following keywords to your package.json:
  -  `chai-plugin`
  -  `browser` if your plugin works in the browser as well as Node.js
  -  `browser-only` if your plugin does not work with Node.js

### Related Projects

- [chaijs / chai-docs](https://github.com/chaijs/chai-docs): The chaijs.com website source code.
- [chaijs / assertion-error](https://github.com/chaijs/assertion-error): Custom `Error` constructor thrown upon an assertion failing.
- [chaijs / deep-eql](https://github.com/chaijs/deep-eql): Improved deep equality testing for Node.js and the browser.
- [chaijs / type-detect](https://github.com/chaijs/type-detect): Improved typeof detection for Node.js and the browser.
- [chaijs / check-error](https://github.com/chaijs/check-error): Error comparison and information related utility for Node.js and the browser.
- [chaijs / loupe](https://github.com/chaijs/loupe): Inspect utility for Node.js and browsers.
- [chaijs / pathval](https://github.com/chaijs/pathval): Object value retrieval given a string path.
- [chaijs / get-func-name](https://github.com/chaijs/get-func-name): Utility for getting a function's name for node and the browser.

### Contributing

Thank you very much for considering to contribute!

Please make sure you follow our [Code Of Conduct](https://github.com/chaijs/chai/blob/master/CODE_OF_CONDUCT.md) and we also strongly recommend reading our [Contributing Guide](https://github.com/chaijs/chai/blob/master/CONTRIBUTING.md).

Here are a few issues other contributors frequently ran into when opening pull requests:

- Please do not commit changes to the `chai.js` build. We do it once per release.
- Before pushing your commits, please make sure you [rebase](https://github.com/chaijs/chai/blob/master/CONTRIBUTING.md#pull-requests) them.
