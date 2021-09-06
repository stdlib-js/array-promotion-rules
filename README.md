<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# Promotion Rules

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] [![dependencies][dependencies-image]][dependencies-url]

> Return the array [data type][@stdlib/array/dtypes] with the smallest size and closest "kind" to which array [data types][@stdlib/array/dtypes] can be **safely** cast.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->

<section class="installation">

## Installation

```bash
npm install @stdlib/array-promotion-rules
```

</section>

<section class="usage">

## Usage

```javascript
var promotionRules = require( '@stdlib/array-promotion-rules' );
```

#### promotionRules( \[dtype1, dtype2] )

If provided [data types][@stdlib/array/dtypes], returns the array [data type][@stdlib/array/dtypes] with the smallest size and closest "kind" to which array [data types][@stdlib/array/dtypes] can be **safely** cast.

```javascript
var out = promotionRules( 'float32', 'uint32' );
// returns 'float64'
```

If not provided [data types][@stdlib/array/dtypes], the function returns a promotion table.

```javascript
var out = promotionRules();
// returns {...}

var f32 = out[ 'float32' ];
// returns {...}

var rule = f32[ 'uint32' ];
// returns 'float64'
```

If provided an unrecognized or unsupported `dtype`, the function returns `null`.

```javascript
var out = promotionRules( 'foo', 'generic' );
// returns null
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

## Notes

-   If a [data type][@stdlib/array/dtypes] to which [data types][@stdlib/array/dtypes] can be safely cast does **not** exist (or is not supported), the function returns `-1`.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var dtypes = require( '@stdlib/array-dtypes' );
var promotionRules = require( '@stdlib/array-promotion-rules' );

var DTYPES;
var dt1;
var dt2;
var dt;
var i;
var j;

// Get the list of supported array data types:
DTYPES = dtypes();

// Print the promotion rule for each pair of array data types...
for ( i = 0; i < DTYPES.length; i++ ) {
    dt1 = DTYPES[ i ];
    for ( j = 0; j < DTYPES.length; j++ ) {
        dt2 = DTYPES[ j ];
        dt = promotionRules( dt1, dt2 );
        console.log( '(%s, %s) => %s', dt1, dt2, dt );
    }
}
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   [`@stdlib/array/dtypes`][@stdlib/array/dtypes]: list of array data types.
-   [`@stdlib/array/safe-casts`][@stdlib/array/safe-casts]: return a list of array data types to which a provided array data type can be safely cast.
-   [`@stdlib/ndarray/promotion-rules`][@stdlib/ndarray/promotion-rules]: return the ndarray data type with the smallest size and closest kind to which ndarray data types can be safely cast.

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

Copyright &copy; 2016-2021. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-promotion-rules.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-promotion-rules

[test-image]: https://github.com/stdlib-js/array-promotion-rules/actions/workflows/test.yml/badge.svg
[test-url]: https://github.com/stdlib-js/array-promotion-rules/actions/workflows/test.yml

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-promotion-rules/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-promotion-rules?branch=main

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-promotion-rules.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-promotion-rules/main

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-promotion-rules/main/LICENSE

<!-- <related-links> -->

[@stdlib/array/dtypes]: https://github.com/stdlib-js/array-dtypes

[@stdlib/array/safe-casts]: https://github.com/stdlib-js/array-safe-casts

[@stdlib/ndarray/promotion-rules]: https://github.com/stdlib-js/ndarray-promotion-rules

<!-- </related-links> -->

</section>

<!-- /.links -->
