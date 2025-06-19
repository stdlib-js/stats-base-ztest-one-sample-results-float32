<!--

@license Apache-2.0

Copyright (c) 2025 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Float32Results

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Create a one-sample Z-test single-precision floating-point results object.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/stats-base-ztest-one-sample-results-float32
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm`][esm-url] branch (see [README][esm-readme]).
-   If you are using Deno, visit the [`deno`][deno-url] branch (see [README][deno-readme] for usage intructions).
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd`][umd-url] branch (see [README][umd-readme]).

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

To view installation and usage instructions specific to each branch build, be sure to explicitly navigate to the respective README files on each branch, as linked to above.

</section>

<section class="usage">

## Usage

```javascript
var Float32Results = require( '@stdlib/stats-base-ztest-one-sample-results-float32' );
```

#### Float32Results( \[arg\[, byteOffset\[, byteLength]]] )

Returns a one-sample Z-test single-precision floating-point results object.

```javascript
var results = new Float32Results();
// returns {...}
```

The function supports the following parameters:

-   **arg**: an [`ArrayBuffer`][@stdlib/array/buffer] or a data object (_optional_).
-   **byteOffset**: byte offset (_optional_).
-   **byteLength**: maximum byte length (_optional_).

A data object argument is an object having one or more of the following properties:

-   **rejected**: boolean indicating whether the null hypothesis was rejected.
-   **alternative**: the alternative hypothesis (e.g., `'two-sided'`, `'less'`, or `'greater'`).
-   **alpha**: significance level.
-   **pValue**: p-value.
-   **statistic**: test statistic.
-   **ci**: confidence interval as a [`Float32Array`][@stdlib/array/float32].
-   **nullValue**: mean under the null hypothesis.
-   **sd**: standard error of the mean.

#### Float32Results.prototype.rejected

Boolean indicating whether the null hypothesis was rejected.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.rejected;
// returns <boolean>
```

#### Float32Results.prototype.alternative

The alternative hypothesis.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.alternative;
// returns <string>
```

#### Float32Results.prototype.alpha

Significance level.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.alpha;
// returns <number>
```

#### Float32Results.prototype.pValue

The test p-value.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.pValue;
// returns <number>
```

#### Float32Results.prototype.statistic

The test statistic.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.statistic;
// returns <number>
```

#### Float32Results.prototype.ci

Confidence interval.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.ci;
// returns <Float32Array>
```

#### Float32Results.prototype.nullValue

Mean under the null hypothesis.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.nullValue;
// returns <number>
```

#### Float32Results.prototype.sd

Standard error of the mean.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.sd;
// returns <number>
```

#### Float32Results.prototype.toString( \[options] )

Serializes a results object to a formatted string.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.toString();
// returns <string>
```

The method supports the following options:

-   **digits**: number of digits to display after decimal points. Default: `4`.
-   **decision**: boolean indicating whether to show the test decision. Default: `true`.

Example output:

```text

One-sample Z-test

Alternative hypothesis: True mean is less than 1.0

    pValue: 0.0406
    statistic: 9.9901
    95% confidence interval: [9.7821, 10.4451]

Test Decision: Reject null in favor of alternative at 5% significance level

```

#### Float32Results.prototype.toJSON( \[options] )

Serializes a results object as a JSON object.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.toJSON();
// returns {...}
```

`JSON.stringify()` implicitly calls this method when stringifying a results instance.

#### Float32Results.prototype.toDataView()

Returns a [`DataView`][@stdlib/array/dataview] of a results object.

```javascript
var results = new Float32Results();
// returns {...}

// ...

var v = results.toDataView();
// returns <DataView>
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   A results object is a [`struct`][@stdlib/dstructs/struct] providing a fixed-width composite data structure for storing one-sample Z-test results and providing an ABI-stable data layout for JavaScript-C interoperation.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var Float32Array = require( '@stdlib/array-float32' );
var Results = require( '@stdlib/stats-base-ztest-one-sample-results-float32' );

var results = new Results({
    'rejected': true,
    'alpha': 0.05,
    'pValue': 0.3364,
    'statistic': 11.7586,
    'nullValue': 0.0,
    'sd': 0.4563,
    'ci': new Float32Array( [ 9.9983, 11.4123 ] ),
    'alternative': 'two-sided'
});

var str = results.toString({
    'format': 'linear'
});
console.log( str );
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2025. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-base-ztest-one-sample-results-float32.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-base-ztest-one-sample-results-float32

[test-image]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-base-ztest-one-sample-results-float32/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-base-ztest-one-sample-results-float32?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-base-ztest-one-sample-results-float32.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-base-ztest-one-sample-results-float32/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/tree/deno
[deno-readme]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/tree/umd
[umd-readme]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/tree/esm
[esm-readme]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/stats-base-ztest-one-sample-results-float32/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-base-ztest-one-sample-results-float32/main/LICENSE

[@stdlib/dstructs/struct]: https://github.com/stdlib-js/dstructs-struct

[@stdlib/array/dataview]: https://github.com/stdlib-js/array-dataview

[@stdlib/array/float32]: https://github.com/stdlib-js/array-float32

[@stdlib/array/buffer]: https://github.com/stdlib-js/array-buffer

</section>

<!-- /.links -->
