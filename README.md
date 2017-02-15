> [htmlhint](https://github.com/yaniswang/HTMLHint) wrapper for [gulp](https://github.com/wearefractal/gulp) to validate your HTML


## Usage

First, install `gulp-htmlformhint` as a development dependency:

```shell
npm install --save-dev gulp-htmlformhint
```

Then, add it to your `gulpfile.js`:

```javascript
var htmlhint = require("gulp-htmlformhint");

gulp.src("./src/*.html")
	.pipe(htmlhint())
```



## API

### htmlhint(options)

See all rules here: [https://github.com/yaniswang/HTMLHint/wiki/Rules](https://github.com/yaniswang/HTMLHint/wiki/Rules)

If options is empty, task use standard options.

#### options.htmlhintrc
Type: `String`
Default value: `null`

If this filename is specified, options and globals defined there will be used. Task and target options override the options within the `htmlhintrc` file. The `htmlhintrc` file must be valid JSON and looks something like this:

```json
{
  "tag-pair": true,
}
```

```javascript
var htmlhint = require("gulp-htmlformhint");

gulp.src("./src/*.html")
	.pipe(htmlhint('.htmlhintrc'))
```


## Reporters

### Default reporter
```javascript
var htmlhint = require("gulp-htmlformhint");

gulp.src("./src/*.html")
	.pipe(htmlhint())
	.pipe(htmlhint.reporter())
```


### Fail reporter

Use this reporter if you want your task to fail in case of a HTMLHint Error.
It also prints a summary of all errors in the first bad file.

```javascript
var htmlhint = require("gulp-htmlformhint");

gulp.src("./src/*.html")
	.pipe(htmlhint())
	.pipe(htmlhint.failReporter())
```

Optionally, you can pass the `htmlhint.failReporter` a config object

__Plugin options:__

- *suppress*

  When set to `true`, it does not display file errors on failure.
  Use in conjunction with the default and/or custom reporter(s).
  Prevents duplication of error messages when used along with another reporter.

  ```javascript
  var htmlhint = require("gulp-htmlformhint");

  gulp.src("./src/*.html")
	  .pipe(htmlhint())
	  .pipe(htmlhint.reporter("htmlhint-stylish"))
	  .pipe(htmlhint.failReporter({ suppress: true })
  ```

## License

License
================

gulp-htmlformhint is released under the MIT license:

> The MIT License
>
> Permission is hereby granted, free of charge, to any person obtaining a copy
> of this software and associated documentation files (the "Software"), to deal
> in the Software without restriction, including without limitation the rights
> to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the Software is
> furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in
> all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
> AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
> OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
> THE SOFTWARE.

[npm-url]: https://npmjs.org/package/gulp-htmlformhint
[npm-image]: https://badge.fury.io/js/gulp-htmlformhint.svg

