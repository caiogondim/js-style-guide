# JavaScript Style Guide (Work in Progress)

<img
  src="https://raw.github.com/caiogondim/js-style-guide/master/logo.png"
  alt="JS Style Guide logo" align="right" width="200px"
/>

My remix of everybody's JavaScript Style Guide with some Python inspiration.

> There should be one - and preferably only one - obvious way to do it.
> - Zen of Python

## Strings

- Use only double quotes. Although single quotes is less noisy, double quote is
the only valid format in JSON. To keep things consistent in all possible
scenarios, just use double quotes.

```javascript
// bad
var foo = 'bar'

// good
var foo = "bar"

// bad
var nameFull = 'John ' + this.nameLast

// good
var nameFull = "John " + this.nameLast
```


- Strings longer than 80 characters should be written across multiple lines
using string concatenation.

```javascript
// bad
var errorMessage = 'This is a super long error that was thrown because of Batman. When you stop to think about how Batman had anything to do with this, you would get nowhere fast.';

// bad
var errorMessage = 'This is a super long error that \
was thrown because of Batman. \
When you stop to think about \
how Batman had anything to do \
with this, you would get nowhere \
fast.';


// good
var errorMessage = 'This is a super long error that ' +
  'was thrown because of Batman. ' +
  'When you stop to think about ' +
  'how Batman had anything to do ' +
  'with this, you would get nowhere ' +
  'fast.';
```

## Reference

- [NPM Coding Style](https://npmjs.org/doc/coding-style.html)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- [Effective Go](http://golang.org/doc/effective_go.html)
- [Idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
