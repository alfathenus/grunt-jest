# grunt-jest v0.1.0

Grunt task to run tests with [Jest](http://facebook.github.io/jest/).



## Getting Started
This plugin requires Grunt `~0.4.0`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-jest --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-jest');
```



## Run tests
_Run this task with the `grunt jest` command._

Task options may be specified according to the grunt [Configuring tasks](http://gruntjs.com/configuring-tasks) guide.
### Options

#### config
Type: `String` srcpath

The path to a jest config file specifying how to find and execute tests. If no rootDir is set in the config, the current directory is assumed to be the rootDir for the project.
See (https://facebook.github.io/jest/docs/api.html)


#### coverage
Type: `Boolean`
Default: `false`

Indicates that test coverage information should be collected and reported in the output.

#### maxWorkers
Type: `Number`
Default: Number of cores available on this machine.
Specifies the maximum number of workers the worker-pool will spawn for running tests. This defaults to the number of the cores available on your machine. (its usually best not to override this default).

#### onlyChanged
Type: `Boolean`
Default: `false`

Attempts to identify which tests to run based on which files have changed in the current repository. Only works if you\'re running tests in a git repository at the moment.

#### runInBand
Type: `Boolean`
Default: `false`

Run all tests serially in the current process (rather than creating a worker pool of child processes that run tests). This is sometimes useful for debugging, but such use cases are pretty rare.

#### testEnvData
Type: `String`

A JSON object (string) that specifies data that will be made available in the test environment (via jest.getTestEnvData()).

#### testPathPattern
Type: `String`

A regexp pattern string that is matched against all tests paths before executing the test.

#### noHighlight
Type: `Boolean`
Default: `false`

Disables test results output highlighting

#### colors
Type: `Boolean`
Default: `false`

Forces test results output highlighting (even if stdout is not a TTY)

#### noStackTrace
Type: `Boolean`
Default: `false`

Disables stack trace in test results output

#### verbose
Type: `Boolean`
Default: `false`

Display individual test results with the test suite hierarchy.

#### watch
Type: `String`

Watch files for changes and rerun tests related to changed files. If you want to re-run all tests when a file has changed, you can call Jest using `--watch=all`.

#### bail
Type: `Boolean`
Default: `false`

Exit the test suite immediately upon the first failing test.

#### useStderr
Type: `Boolean`
Default: `false`

Divert all output to stderr.

#### cache
Type: `Boolean`
Default: `true`

Whether to use the preprocessor cache. Disable the cache using --no-cache.

#### json
Type: `Boolean`
Default: `false`

Prints the test results in JSON. This mode will send all other test output and user messages to stderr.

#### testRunner
Type: `String`

Allows to specify a custom test runner. Jest ships with Jasmine 1 and 2 which can be enabled by setting this option to `jasmine1` or `jasmine2`. The default is `jasmine2`. A path to a custom test runner can be provided: `<rootDir>/path/to/testRunner.js`.

#### logHeapUsage
Type: `Boolean`
Default: `false`

Logs the heap usage after every test. Useful to debug memory leaks. Use together with `--runInBand` and `--expose-gc` in node.

#### watchman
Type: `Boolean`
Default: `true`

Whether to use watchman for file crawling. Disable using --no-watchman.

#### watchman
Type: `Boolean`
Default: `false`

Prevent tests from printing messages through the console.



### Usage Examples

```js
jest: {
  options: {
    coverage: true,
    testPathPattern: /.*-test.js/
  }
}
```
