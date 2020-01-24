# NPM Tips and Tricks

The npm is the original `Node Package Manager`. Currently, `bower` is created to overcome some of the `npm` short comings. (Need more info on this and possible some comparison)

## create a plain nodejs project

```
  mkdir myapp
  $ cd myapp
```

A quick reminder of all options is available from the command line:

```
  $ npm help
```

To get more specific help run the following command:
```
  $ npm help <command>
  $ npm help access
  $ npm help install
```
This will open a browser with the detailed description of the command.

npm version, patch minor and major
```
  $ npm version
  $ npm version patch
  $ npm version minor
  $ npm version major
```
You may also need to rebuild C++ addons when a new major version of Node is released:
```
  $ npm rebuild
```
Use the npm init command to create a package.json file for your application. For more information on how package.json works, see Specifics of npm’s package.json handling.
```
  $ npm init
  $ npm init -y // will create package.js silently
  $ npm init -f
  $ npm config set init.author.name <name>
  $ npm config set init.author.email <email>
  $ npm run <script entry in package.js>
  $ npm ls --depth 0 // list packages installed at project level
  $ npm ls -g --depth 0 // list packages installed at global level
```
You can also shorten --save with -S and --save-dev with -D.

In some cases you may want to force an exact package version rather than based on a range or approximate. The --save-exact optional flag used in conjunction with the --save flag will do that for you.

  $ npm install <package_name> --save --save-exact

To automate the `package.js` creation user the following commands;

```
  $ npm set init.author.name "$NAME"
  $ npm set init.author.email "$EMAIL"
  $ npm set init.author.url "$SITE"
  $ npm init
```

You’ve chosen your packages and installed the dependencies. Let’s list what we have:
```
  $ npm list
```
you can get the currently installed version of a package by executing:
```
  $ npm view <pkg> version
```
If you’re having any issues with an npm package, you might have to remove it from the npm cache before attempting to install it again.
```
  $ npm clean <pkg>
  $ npm install <pkg>
```
(ls, la and ll can be used as aliases for list).
The list shows everything: packages, sub-packages, sub-packages of sub-packages etc. Limit the output to top-level-only packages using:

```
  $ npm list --depth=0
```
A package homepage can be opened with:
```
  $ npm home <package>
```
This only works if your system can open a browser – it will fail on OS Server editions. Similarly, you can open a package’s GitHub repository:
```
  $ npm repo <package>
```
or its documentation:
```
  $ npm docs <package>
```
or the current list of bugs:
```
  $ npm bugs <package>
```
npm list reports when you have extraneous packages installed — those which are no longer referenced in your package.json file. You can npm uninstall each separately or remove them all with:
```
  $ npm prune
```
If you add the --production flag or have the NODE_ENV environment variable set to production, packages specified as devDependencies in package.json will also be removed.

## Locking-Down Dependencies

By default, npm references package version numbers with the caret (^) character when installing a package with --save or --save-dev. This pins the package to its major version number. For example, ^1.5.1 permits anything from that version up to but NOT including 2.0.0 to be installed when npm update is run.

The more conservative tilde (~) character pins the package to the minor version. For example, ~1.5.1 permits anything from that version up to but not including 1.6.0 to be installed when npm update is run. The tilde prefix can be set as the default with:
```
  $ npm config set save-prefix="~"
```
For those who are paranoid about any updates which could break your system, you can configure npm to use exact version numbers only:
```
  $ npm config set save-exact true
```
Alternatively, you can shrinkwrap your project using:
```
  $ npm shrinkwrap
```
This generates an `npm-shrinkwrap.json` file containing the specific versions of the dependencies you’re using. This file is used by default and will override `package.json` when running npm install.

See (https://docs.npmjs.com/cli/shrinkwrap)[https://docs.npmjs.com/cli/shrinkwrap] for more information.

## Finding Outdated Modules

How do you know when a dependency has been updated? The process I used for many months was to list my dependencies (npm list --depth=0), search for the package on npmjs.com and manually check which version numbers had changed. Hours of fun. Fortunately, there’s a significantly easier option:
```
  $ npm outdated
```
Or npm outdated -g for global packages such as npm itself.

You can also view the current version of an individual package:
```
  $ npm list <package>
```
and examine the current and historical versions:
```
  $ npm view <package> versions
```
npm view <package> displays all information about an individual package including its dependencies, keywords, update dates, contributors, repository, licence, etc.

## Using Development Packages

When developing packages you often want to try them in other projects or run them from any directory (if your application supports it). There’s no need to publish the package to the npm registry and install globally – just use:
```
  $ npm link
```
from the package folder. This creates a symlink in the global folder for that package. You will see the reference when using:
```
	$ npm list -g --depth=0
```
or
```
	$ npm outdated -g
```
You can now run package from the command line or include it in any project with require.
Alternatively, you also can declare dependencies by filepath in package.json, e.g.
```
	"dependencies": {
		"myproject": "file:../myproject/"
	}
```
So those are some of my favorite npm tricks but have I missed one of yours? Comments are welcome…

This command prompts you for a number of things, such as the name and version of your application. For now, you can simply hit RETURN to accept the defaults for most of them, with the following exception:
```
	entry point: (index.js)
```
Enter app.js, or whatever you want the name of the main file to be. If you want it to be index.js, hit RETURN to accept the suggested
```
	default file name.
```
Now install Express in the myapp directory and save it in the dependencies list. For example:
```
	$ npm install express --save
```
To install Express temporarily and not add it to the dependencies list:
```
	$ npm install express --no-save
```
You can do that using an optimized npm publish created by dominictarr.
```
	$ npm i -g npm-atomic-publish
```
Using the command below, you can remove devDependencies after npm install. This is useful in some set ups where you deploy to a CI environment, which installs everything so that it can run your Grunt build, or something, and then deploys to the live servers.

```
	$ npm prune --production
```

## For more information see
* (https://docs.npmjs.com/)[https://docs.npmjs.com/]
* (https://github.com/sindresorhus/awesome-npm)[https://github.com/sindresorhus/awesome-npm]
