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

### Mutable versus immutable methods

A pattern used on the Qt framework is to use forms of a verb to indicate wheter
the method will change or not the original object. Use **present** for methods
that change the object. Use **past participle** for methods that returns a
transformed value without mutating the original object.

```javascript
// Immutable method
var str = " Lorem ";
str.trimmed();
console.log(str); // => " Lorem "

// Mutable method
str.trim();
console.log(str); // => "Lorem"
```

### Conventions

Some very popular conventions used in programming and in JavaScript.

#### `err` for error

Specially common in Nodejs land. Avoid to use `e` for an error variable. It not
meaningfull and lots of people also uses `e` for events and elements.

```javascript
// bad
http.get("http://www.google.com/index.html", function(res) {
  console.log("Got response: " + res.statusCode);
}).on('error', function(e) {
  console.log("Got error: " + e.message);
});

// good
http.get("http://www.google.com/index.html", function(res) {
  console.log("Got response: " + res.statusCode);
}).on('error', function(err) {
  console.log("Got error: " + err.message);
});
```

#### `ev` for event

Just like `err`, avoid to use `e` for events.

```javascript
// bad
$("body").on("click", function(e) {
  console.log("<body> was clicked");
});

// good
$("body").on("click", function(ev) {
  console.log("<body> was clicked");
});
```

#### `el` for element

As with events and errors, avoid to use `e` for variables that holds references
for DOM elements.

```javascript
// bad
var e = $("body");

// good
var el = $(" body");
```

#### Loops

If you need to use `for` or `while` loops, start the counter with the letter
`i`. For nested loops, use the letters `j`, `k` and `l`. If you need more than
4 nested loops, something is probably wrong with your code.

This is an idiom very used throught out almost every programming language.

```javascript
// bad
for (var count1 = 0; count1 < 10; count1++) {
  for (var count2 = 0; count2 < 20; count2++) {
    // le code
  }
}

// good
for (var i = 0; i < 10; i++) {
  for (var j = 0; j < 10; j++) {
    // le code
  }
}
```

## Reference

- [NPM Coding Style](https://npmjs.org/doc/coding-style.html)
- [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)
- [Effective Go](http://golang.org/doc/effective_go.html)
- [Idiomatic.js](https://github.com/rwaldron/idiomatic.js/)
- [Ariya Hidayat's blog](http://ariya.ofilabs.com/2014/02/javascript-array-slice-vs-splice.html)
