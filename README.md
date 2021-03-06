mocha-jsxhint
------------

Run jsxhint as Mocha tests.

To install in your node.js project as devDependency, run this command, in the root of your project
```
npm install mocha-jsxhint --save-dev
```

usage
-----
Mocha defaults to looking for your test specs in the `test` folder of your project.
Add this file as `test/_jsxhint-spec.js` in your project, with the following content:

```js
require('mocha-jsxhint')();
```

That is it you are done.

To grep only the jshint test, just do
```
mocha --grep jsxhint
```

configuring jsxhint
------------------
In the root of your project you can add a `.jshintignore` file, where each line is a file or directory for jshint to ignore
and not check for errors. (see this project for an example)

At the root of your project you can add a `.jshintrc` file, that specifies what options you want jshint to run with
(see this project for an example)

You can also add a `.jshintrc` file to any subdirectory of your project, to override the .jshintrc settings in the root.
For example in this project I allow some global variables in the `test` folder. Global variables that are set when I
run mocha tests. Global variables that are only allowed to be used, in the .js files in the test folder

Why?
---
This module was created to:

- Make adding jshint testing to a project using Mocha as easy as possible
- Make it easy to piggyback on all the different Mocha reporters (dot, spec, teamcity etc) for jshint output
- Make sure that you get a click-able link directly to the problem in WebStorm, when jshint fails
- Make sure that there is no unnecessary noise in the test output
