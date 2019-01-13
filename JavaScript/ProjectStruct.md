# Project Structure
The following link is the Sample project for this document
* [https://github.com/Esri/enterprise-build-sample-js](https://github.com/Esri/enterprise-build-sample-js)

The subsequent sections provide a list of tools used in this project:

# bower
# jshint
# grunt
Grunt is a JavaScript Task Runner which can be used as a command line tool for JavaScript objects. It is a task manager written on top of NodeJS. This tutorial explains how to use GruntJS to automate the build and deployment process in simple and easy steps.

Grunt is a task runner, similar to ant.

The following is a list of usefule grunt plugins
<table>
<tr>
<th>
Plugin
</th>
<th>
Description
</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-jshint" target="_blank">contrib-jshint</a>
</td>
<td>
Validate files using jshint
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-uglify" target="_blank">contrib-uglify</a>
</td>
<td>
Minify JS files using UglifyJS
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-watch" target="_blank">contrib-watch</a>
</td>
<td>
Run tasks whenever watched files are changed
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-clean" target="_blank">contrib-clean</a>
</td>
<td>
Clean up files and folders
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-copy" target="_blank">contrib-copy</a>
</td>
<td>
Copy files and folders
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-concat" target="_blank">contrib-concat</a>
</td>
<td>
Combine files into a single file
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-cssmin" target="_blank">contrib-cssmin</a>
</td>
<td>
Compress CSS files
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-less" target="_blank">contrib-less</a>
</td>
<td>
Compile LESS files to CSS
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-imagemin" target="_blank">contrib-imagemin</a>
</td>
<td>
Minify PNG, JPG, and GIFs
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-compass" target="_blank">contrib-compass</a>
</td>
<td>
Compile SASS to CSS using Compass
</td>
</tr>
<tr>
<td>
<a href="https://www.npmjs.org/package/grunt-contrib-htmlmin" target="_blank">contrib-htmlmin</a>
</td>
<td>
Minify HTML files
</td>
</tr>
</tbody>
</table>

For the full list of packages, visit the [http://gruntjs.com/plugins](http://gruntjs.com/plugins).
Now that we have the packages we need defined, let's install them.

the following is a sample Grunt.js file;

  module.exports = function (grunt) {
    // Build customizations would be left up to developer to implement.
    grunt.loadNpmTasks('grunt-dojo');
    grunt.loadNpmTasks('grunt-contrib-copy');
    grunt.loadNpmTasks('grunt-contrib-clean');
    grunt.loadNpmTasks('grunt-replace');
    grunt.loadNpmTasks('grunt-karma');
    grunt.loadNpmTasks('grunt-contrib-watch');
    grunt.loadNpmTasks('grunt-contrib-connect');
    grunt.loadNpmTasks( 'grunt-contrib-jshint' );

    var port = grunt.option('port') || 8000;

    grunt.initConfig({

      clean: {
        build: {
          src: ['dist/', 'build-temp/', 'build-src/js/buildProject/']
        },
        postbuild: ['build-temp/'],
        test: ['test-reports/, coverage/']
      },

      copy: {
        prebuild: {
        	files: [
        	// copy project packages from src to build-src
        	{
        		expand: true,
        		cwd: 'web/js/buildProject',
        		src: ['**'],
        		dest: './build-src/js/buildProject'
        	},
        	// copy project non-package artifacts direct to dist
        	{
        		expand: true,
        		cwd: 'web',
        		src: ['*', 'js/data/**', 'js/images/**'],
        		dest: './dist/'
        	},
        	// copy project node dependecies to dist
        	{
        		expand: true,
        		cwd: './node_modules',
        		src: ['dojo-themes/**'],
        		dest: './dist'
        	}]
        },
        // copy all the layer files specified in the profile.js
        // created by the dojo build to the dist dir
        postbuild: {
        	files: [{
        		expand: true,
        		cwd: 'build-temp/js',
        		src: ['dojo/dojo.js', 'esri/layers/VectorTileLayerImpl.js'],
        		dest: './dist/js'
        	}]
        }
      },

  	replace: {
  		dist: {
  			options: {
  				patterns: [
  					// replace the hosted jsapi with the dojo build layer file
  					{ match: /\/\/js.arcgis.com\/4.3\/"/g, replacement: 'js/dojo/dojo.js"'},
  					// remove the reference to your app package
  					{ match: /\/\/ DELETE FROM HERE[\s\S]*\/\/ TO HERE/, replacement: ''},
  					// clean up any debug flags to make the app ready for production
  					{ match: /isDebug[\s]*:[\s]*true/, replacement: 'isDebug: false'}
  				]
  			},
  			files: [{src:'web/index.html', dest:'dist/index.html'}]
  		}
  	},

      dojo: {
        dist: {
          options: {
            profile: '../../build/buildProject.profile.js'
          }
        },
        options: {
          dojo: './dojo/dojo.js',
          load: 'build',
  		releaseDir: '../../build-temp/js',
          cwd: './build-src/js',
          basePath: '.'
        }
      },

  	karma: {
  	  options: {
          // get defaults from karma config
          configFile: 'karma.conf.js',
          // run all tests once then exit
          singleRun: true,
          // only show error messages
          logLevel: 'ERROR',
        },
  	  unit: {
  		  options:{
  			singleRun: true,
  			captureTimeout:30000,
  			reporters : ['junit', 'coverage'],
  			junitReporter: {
  			  outputDir: 'test-reports', // results will be saved as $outputDir/$browserName.xml
  			  outputFile: undefined, // if included, results will be saved as $outputDir/$browserName/$outputFile
  			  suite: '', // suite will become the package name attribute in xml testsuite element
  			  useBrowserName: true // add browser name to report and classes names
  			}
  		  }
  	  }
  	},
  	jshint: {
  		options: {
  			curly: false,
  			eqeqeq: true,
  			immed: true,
  			latedef: true,
  			newcap: true,
  			noarg: true,
  			sub: true,
  			undef: true,
  			eqnull: true,
  			browser: true,
  			expr: true,
  			globals: {
  				head: false,
  				module: false,
  				console: false,
  				unescape: false,
  				define: false,
  				exports: false
  			}
  		},
  		files: [ 'Gruntfile.js', 'web/js/buildProject/**/*.js' ]
  	},
  	connect: {
  	  	server: {
  	  		options: {
  	  			port: port,
  	  			livereload: true,
  	  			open: true,
  	  			base: ['web','node_modules']
  	  		}
  	  	}
  	  },
  	  watch: {
  		options: {
  			livereload: true
  		},
  		js: {
  			files: [ 'Gruntfile.js', 'web/js/buildProject/**/*.js' ],
  			tasks: ['js']
  		},
  		html: {
  			files: [ 'web/index.html']
  		}
  	}
    });

    // Serve dev app locally
    grunt.registerTask( 'serve', [ 'connect', 'watch' ] );

    grunt.registerTask('build', ['clean:build', 'copy:prebuild', 'dojo', 'copy:postbuild', 'replace', 'clean:postbuild']);

    grunt.registerTask('test', ['jshint', 'karma']);

    	// JS task
  	grunt.registerTask( 'js', [ 'jshint'] );

  };

# karma

Karma is a JavaScript browser-based test runner created by the AngularJS team. Jasmine is the testing framework that we talked about in the getting started with unit testing for AngularJS post, and Karma provides helpful tools that make it easier to us to call our Jasmine tests whilst we are writing code. karma can only based with web-based project.
For bakend testing use Mocha and Chai. 

## Installtion:

    npm -g install karma          // global installation
    npm install karma -save-dev   // local installation

This installtion will include the following plugins;

* karma-chrom-launcher
* karma-coverage
* karma-jasmine

there are also support for other browsers.

## Configuration

Before you run Karma you must configure it. This is the most important step in setting up Karma. The easiest way to get started is to run the init command. In a command window, navigate to your project folder and enter:

  $ karma init karma.conf.js // prior to running this command you must install the karam globally

this will generate the default karma configuration file. You can name the file whatever you want. This is a wizard and it will prompt you for a series of questions. The questions are easy to answer and the net result is a properly structured Karma configuration file.

the following is a sample default file generated.

  // Karma configuration
  // Generated on Wed Sep 06 2017 09:21:52 GMT-0400 (Eastern Daylight Time)

  module.exports = function(config) {
    config.set({
      // base path that will be used to resolve all patterns (eg. files, exclude)
      basePath: '',
      // frameworks to use
      // available frameworks: https://npmjs.org/browse/keyword/karma-adapter
      frameworks: ['jasmine'],
      // list of files / patterns to load in the browser
      files: [
        'test1',
        'test'
      ],
      // list of files to exclude
      exclude: [
      ],
      // preprocess matching files before serving them to the browser
      // available preprocessors: https://npmjs.org/browse/keyword/karma-preprocessor
      preprocessors: {
      },
      // test results reporter to use
      // possible values: 'dots', 'progress'
      // available reporters: https://npmjs.org/browse/keyword/karma-reporter
      reporters: ['progress'],
      // web server port
      port: 9876,
      // enable / disable colors in the output (reporters and logs)
      colors: true,
      // level of logging
      // possible values: config.LOG_DISABLE || config.LOG_ERROR || config.LOG_WARN || config.LOG_INFO || config.LOG_DEBUG
      logLevel: config.LOG_INFO,
      // enable / disable watching file and executing tests whenever any file changes
      autoWatch: true,
      // start these browsers
      // available browser launchers: https://npmjs.org/browse/keyword/karma-launcher
      browsers: ['Chrome'],
      // Continuous Integration mode
      // if true, Karma captures browsers, runs the tests and exits
      singleRun: false,
      // Concurrency level
      // how many browser should be started simultaneous
      concurrency: Infinity
    })
  }

The following file is a customized version of the above file:

  module.exports = function(config) {
    config.set({
      // base path, that will be used to resolve files and exclude
      basePath: '',
      frameworks: ['jasmine', 'dojo'],
      // list of files / patterns to load in the browser
      files: [
        'spec/main.js',
        // all the sources, tests
        {pattern: 'web/js/buildProject/**/*', included: false},
        {pattern: 'spec/*.js', included: false}
      ],

      // uncomment the following for code coverage
      // preprocessors: {
      //   // source files, that you wanna generate coverage for
      //   // do not include tests or libraries
      //   // (these files will be instrumented by Istanbul)
      //   'src/**/*.js': ['coverage']
      // },


      // test results reporter to use
      // possible values: dots || progress
      reporters: [
        'dots', 'junit'
        // uncomment the following line for code coverage
        // , 'coverage'
      ],

  	junitReporter : {
  	  outputFile: 'test-results.xml'
  	},


      // web server port
      port: 9876,

      // proxy for cross domain requests
      proxies:  {
        '/arcgis/': 'http://imagery.arcgisonline.com/arcgis/'
      },


      // cli runner port
      runnerPort: 9100,


      // enable / disable colors in the output (reporters and logs)
      colors: true,


      // level of logging
      // possible values: LOG_DISABLE || LOG_ERROR || LOG_WARN || LOG_INFO || LOG_DEBUG
      logLevel: config.LOG_INFO,


      // enable / disable watching file and executing tests whenever any file changes
      autoWatch: false,

      // Start these browsers, currently available:
      // - Chrome
      // - ChromeCanary
      // - Firefox
      // - Opera
      // - Safari
      // - PhantomJS
      // NOTE: you may need to first set it's path in an environment vairable, for example:
      // set FIREFOX_BIN="c:\Program Files (x86)\Mozilla Firefox\firefox.exe"
      // see: http://karma-runner.github.io/0.10/config/browsers.html
      browsers: [
        'Chrome'
        // add the name (from above) for each additional
        // browser you want to test below
        // , 'Firefox'
      ],


      // uncomment the following for coverage options
      // see: https://github.com/karma-runner/karma-coverage#options
      // coverageReporter: {
      //   type : 'text',
      //   dir: 'coverage/'
      // },


      // Continuous Integration mode
      // if true, it capture browsers, run tests and exit
      singleRun: true
    });
  };

You’ll need to answer the following questions:

1. What testing framework do you want to use?
Jasmine, Mocha, and QUnit are installed by default and can be referenced by name, but if you have installed another one you should name it here. Because each framework is a plugin, you will need to list the plugin file in the plugins section of the configuration file as well (see the sample configuration file below for an example.)

1. Do you want to use Require.js?
Require.js is a lazy-loading framework that many developers use to minimize the initial script load times in the browser. If your project uses is, you need to answer YES to this question.

1. Do you want to capture a browser automatically?
You should respond with the browser name(s) that you want to use, one per line. Remember that you must have the matching –launcher plugin installed for each browser, and that only the karma–chrome-launcher and karma–chromeCanary-launcher plugin are installed by default. Entering a blank line will move you to the next question.

1. What is the location of your source and test files?
This path is relative to the location of Karma. You can enter an absolute path and be assured of directing Karma to the right location, or enter a relative path if your files are located below the Karma folder.

1. Should any of the files included by the previous patterns be excluded?
If you use a very broad pattern, you may want to exclude the folder where you store your images, or where there are no .js files to test. Tighter patterns take up more lines in the configuration file, but also eliminate the need for an exclude block.

1. Do you want Karma to watch all the files and run tests on change?
Having Karma run continuously is very helpful as you can see your tests and code evolve in a TDD environment. If you don’t do TDD, you can opt to only run Karma when you are ready to execute your tests.

For the more adventurous or those that need more than just the basic configuration, you can edit the configuration file and tailor Karma to fit your needs. There are four main sections of the configuration file that you’ll want to pay particular attention to: preprocessors, plugins, browsers, and files.

## Preprocessors

Preprocessors enable you to do things to your code before it gets sent to the browser to have the tests run on it. Karma comes with the karma-coffee and karma-html2js preprocessors already installed. I regularly use the karma-coverage preprocessor to show me how much of my code I have covered with my tests. For a complete description of what any individual preprocessor does you should read the documentation on its website.

## Plugins

While Karma comes with several plugins pre-installed, you need to tell it which ones you want to use for running your tests. There are methods for dynamically determining which plugins get used, or you can just list them out. If your project doesn’t change much with respect to how you are testing your code, the static listing is the easiest way to go.

## Browsers

Browser support is critical for JavaScript. Karma comes with launchers pre-installed for Chrome, Chrome-Canary, and PhantomJS. Other launchers need to be installed if you want to test your JavaScript in other browsers. I regularly test in Chrome, IE, and Firefox. Karma takes care of capturing and killing the browser processes for you. This enables you to spend more time developing and less time doing the menial processes associated with testing. The default time allowed to capture any one browser is one minute, which should be more than enough time, but you can change that value via the captureTimeout option in the configuration file. You will also need to tell Karma where the executable files are for all browsers except IE. If you want to capture your browser manually (from a tablet, for example) you can point the browser to http://<hostname>:<port> where <hostname> is the hostname or IP address of the computer where Karma is running, and <port> is the port you specified in the configuration file. By default this is port 9876, but if you have changed it in the port section of your configuration file then use that port.

## Files

You need to tell Karma which files are required to run your project, which files contain your tests, and which files need to be tested. For convenience, in my configuration file I have broken these files into their respective groups, with required files first, test files second, and files to be tested last. The order in which they appear is the order that they will be included in the browser, so depending upon your project you may need to pay attention to it. Each file or group of files can be flagged for being watched by Karma, included in the browser <script> tag, and served by the Karma server. Files that are watched can trigger Karma to run all of the tests again, so pay particular attention to these. If you simply list all of your files, they will be watched, included, and served, which may result in performance loss during testing on older, slower computers.

Karma runs on NodeJS and the configuration is set up using module.exports so that it gets drawn into and consumed by NodeJS. Older versions of Karma did not have this feature, and they were slightly harder to configure correctly. A good sample of a Karma configuration file looks like this:

  module.exports = function(config) {
    config.set({
  	// base path, that will be used to resolve files and exclude
  	basePath: '../..',

  	frameworks: ['jasmine'],

  	// list of files / patterns to load in the browser
  	files: ['test/client/mocks.js', 'static/karma.src.js', 'test/client/*.spec.js'],

  	// list of files to exclude
  	exclude: [],

  	// use dots reporter, as travis terminal does not support escaping sequences
  	// possible values: 'dots', 'progress'
  	reporters: ['progress', 'junit'],

  // will be resolved to basePath (in the same way as files/exclude patterns)
  junitReporter: {outputFile: 'test-results.xml'},

  	// web server port
  	port: 9876,

  	// enable / disable colors in the output (reporters and logs)
  	colors: true,

  	// level of logging
  	// possible values: config.LOG_DISABLE || config.LOG_ERROR || config.LOG_WARN
  	|| config.LOG_INFO || config.LOG_DEBUG
  	logLevel: config.LOG_INFO,

  	// enable / disable watching file and executing tests whenever any file changes
  	autoWatch: true,

  	// Start these browsers, currently available:
  	// - Chrome, ChromeCanary, Firefox, Opera, Safari (only Mac), PhantomJS, IE (only Windows)
  	browsers: [process.env.TRAVIS ? 'Firefox' : 'Chrome'],

  	// If browser does not capture in given timeout [ms], kill it
  	captureTimeout: 20000,

  	// Auto run tests on start (when browsers are captured) and exit
  	singleRun: false,

  	// report which specs are slower than 500ms
  	reportSlowerThan: 500,

  	// compile coffee scripts
  	preprocessors: {'**/*.coffee': 'coffee'},

  	plugins: ['karma-jasmine','karma-chrome-launcher',
  	'karma-firefox-launcher','karma-junit-reporter']
    });
  };

## Running Karma

There are two main ways to run Karma: at the command line or via your IDE. I heavily favor running Karma from my IDE (WebStorm) because it keeps me on the same screen more. Regardless of which method you choose, running Karma does the following:

* Starts a web server in Node.
* Launches the specified browsers with a default URL that points to that web server.
* Attempts to capture the browser session in each browser.
* Upon capture of all browsers, the tests are run and the reports generated.
* If you have opted to have Karma stay running and monitor files, each time one of those files changes the tests will be re-run and the reports re-generated.
* If you have opted to only have Karma run once, each browser session is released and the browser is closed.

## Test Results

Testing is only useful if you can see the results, and Karma has several options available. The progress reporter is inserted into the configuration file that the init process creates by default. This reporter gives you a complete listing of each test that is run, in the order that they are executed, and whether they pass or fail. The dots reporter is included with Karma for those that run Travis. There are other reporters available as plugins (growl, Junit, Teamcity and Coverage) that can help make your testing process easier and more complete. Each reporter must be listed in the reporters section of the configuration file, and some reporters (such as the coverage reporter) require that they be referenced in the preprocessors section as well. The coverage reporter that is included with Karma is Istanbul and I have found it very well suited for my needs and for use with Karma.

## IDE Integration

Part of the beauty of Karma is how easily it can be integrated in to your IDE. Nearly all IDEs have a way to add an external tool that is launched on the command line. Configuring WebStorm 6 and older to run Karma as an external tool is covered in the introductory video that the creator (Vojta Jina) posted via YouTube (http://www.youtube.com/watch?v=MVw8N3hTfCI) and can be found at the 7:39 mark in the video. There is a handy link to this part just below the video. There is also integration built into the upcoming WebStorm 7 (currently accessible via the Early Access Program.) It has been my experience that integrating with WebStorm produces an excellent development environment. Support for configuring external tools isn’t limited to JetBrains products. Visual Studio 2008 or newer in any flavor except the Express versions will allow you to configure external tools to launch from the menu (you would need to create a batch file with the requisite Karma commands in it and tell VS to launch that file.) Sublime is also a heavily favored text editor for web development, and it also supports external tools. As long as your favored IDE supports external tools in some way, you should be able to launch Karma and have it run tests.

## Documentation

The vast majority of what you need to get up and running with Karma is contained in the Karma website. Most any other question can be answered by searching the Google Group or posting a question on Stack Overflow. Documentation for individual plugins will be found with those plugins. For anything that isn’t covered, the Google Group is the best resource to try first, and Stack Overflow is a very close second.

## Actual Experience

A large number of developers don’t test their JavaScript, and they really should. Too many of them think that testing is hard to set up and hard to do, and Karma is proof of the opposite. My team and I use Karma with Jasmine every day of the week. We found the installation and configuration to be fast and easy to follow. We went from downloading NodeJS to running tests via Karma in under an hour. When you consider that my team and I were totally new to testing, let alone testing JavaScript, this is pretty impressive. We chose Karma because it had support for AngularJS without any configuration changes, and because it would let us test our other scripts as well. In each of these areas it has excelled from day #1. We are now preparing to move our project to Yeoman and have no fear about how our tests will work because Yeoman fully supports Karma. We firmly believe that we could not have chosen a better tool to include in our daily routines.

## Summary

Karma is the preferred test runner for projects written with AngularJS and is well on its way to larger acceptance within the greater JavaScript community. Its plugin architecture makes it easily adaptable to other test suites and reporters, all of which add value to the core of Karma. In agile or continuous integration environments, Karma shines as an indispensable tool to development teams, providing an easy and reliable way to modify existing code and craft new code as part of TDD. It is rare that a day goes by without this tool running on my computer.

Website: [http://karma-runner.github.io/](http://karma-runner.github.io/)
Installtion [https://www.npmjs.com/browse/keyword/karma-plugin](https://www.npmjs.com/browse/keyword/karma-plugin)

## For more information See:

* [http://www.bradoncode.com/blog/2015/05/19/karma-angularjs-testing/](http://www.bradoncode.com/blog/2015/05/19/karma-angularjs-testing/)
* [http://www.methodsandtools.com/tools/karma.php](http://www.methodsandtools.com/tools/karma.php)
* [https://groups.google.com/forum/?fromgroups#!forum/karma-users](https://groups.google.com/forum/?fromgroups#!forum/karma-users)
* [http://stackoverflow.com/questions/tagged/karma](http://stackoverflow.com/questions/tagged/karma)
* [http://stackoverflow.com/questions/tagged/karma-runner](http://stackoverflow.com/questions/tagged/karma-runner)

# dojo

Dojo Toolkit is an open source modular JavaScript library (or more specifically JavaScript toolkit) designed to ease the rapid development of cross-platform, JavaScript/Ajax-based applications and web sites.

project home [https://dojotoolkit.org/](https://dojotoolkit.org/)

# unit js
Project home URL : [http://unitjs.com/](http://unitjs.com/)

# jasmine
