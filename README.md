# html-jest-reporter
**A [jest](https://github.com/facebook/jest) test results processor for generating a summary in HTML.**


This plugin was inspired by [jest-html-reporter](https://github.com/Hargne/jest-html-reporter) by Johan Hargne

## Additional Usage of the Plugin
This plugin combines all the Test suite and shows the report in the combined manner at the Top.
It can also show the report on the basis of Number of Positive and Negative Test cases (Pre Condition:
You will have to prefix your test case name by P_ (For positive Test case) or N (For negative Test case))

## Installation
```shell
npm install html-jest-reporter
```

## Usage
Configure Jest to process the test results by adding the following entry to the Jest config (jest.config.js):
```JSON
{
	"testResultsProcessor": "./node_modules/html-jest-reporter"
}
```
Then when you run Jest from within the terminal, a file called *test-report.html* will be created within your root folder containing information about your tests.

### Alternative usage with package.json
Although jest.config.js is specifically created for configuring Jest (and not this plugin), it is possible to configure Jest from within package.json by adding the following as a new line:
```JSON
"jest": { "testResultsProcessor": "./node_modules/html-jest-reporter" }
```

## Node Compatibility
This plugin is compatible with Node version `^4.8.3`

## Configuration
The configurations are done directly within your *package.json* file

### enableCategoryWiseReport (boolean)
*[Default: false]*

This flag enabled the test case category (Positive or Negative) wise reporting.

### outputPath (string)
*[Default: "./test-report.html"]*

The path to where the plugin will output the HTML report. The path must include the filename and end with .html


### Example configuration (package.json)
```JSON
{
	...
	"html-jest-reporter": {
		"pageTitle": "Your test suite",
		"outputPath": "test-report/index.html",
		"includeFailureMsg": false,
		"styleOverridePath": "src/teststyle.css",
		"enableCategoryWiseReport": true
	}
}
```