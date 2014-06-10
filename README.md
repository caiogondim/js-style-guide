# JavaScript Style Guide (Work in Progress)

<img
  src="https://raw.github.com/caiogondim/js-style-guide/master/logo.png"
  alt="JS Style Guide logo" align="right" width="200px"
/>

> A style guide is about consistency. Consistency with this style guide is
> important. Consistency within a project is more important. Consistency within
> one module or function is most important.

> But most importantly: know when to be inconsistent -- sometimes the style guide
> just doesn't apply. When in doubt, use your best judgment. Look at other
> examples and decide what looks best. And don't hesitate to ask!>

> PEP 8, Python


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


## Naming

### Avoid double negatives

```javascript
// bad
foo.disabled = false

// good
foo.enabled = true

// bad
bar.setHidden(false)

// good
bar.setVisible(true)

// bad
kung.invisible = false

// good
kung.visible = true
```

### Verbal actions

```javascript
// bad
status.message("Lorem ipsum")

// good
status.showMessage("Lorem ipsum")

// bad
page.forward()

// good
page.goForward()

// bad
page.backward()

// good
page.goBackwards()
```

## Reference

- [NPM Coding Style](https://npmjs.org/doc/coding-style.html)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- [Effective Go](http://golang.org/doc/effective_go.html)
- [Idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
