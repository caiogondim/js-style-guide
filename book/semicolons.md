## Semicolons

There are a lot of
[FUD](http://en.wikipedia.org/wiki/Fear,_uncertainty_and_doubt) about the
omission of semicolons in JavaScript. It's perfect safe to ommit them and it
removes unnecessary symbols from the code, making it looks cleaner.

Use a `;` only before a leading `(`, `[`, `-`, `+` or `!` at the start of the
line. This prevents the expression from being interpreted as a function call or
property access, respectively.

```javascript
// bad
var foo = 'bar';

// good
var foo = 'bar'

// bad
(x || y).doSomething()

// good
;(x || y).doSomething()

// bad
[a, b, c].forEach(doSomething)

// good
;[a, b, c].forEach(doSomething)
```
And since you minify your production code (right?), in the end it doesn't
matter.
