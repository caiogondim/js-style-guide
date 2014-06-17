# Conventions

Some very popular conventions used in programming and in JavaScript.

## `err` for error

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

## `ev` for event

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

## `el` for element

As with events and errors, avoid to use `e` for variables that holds references
for DOM elements.

```javascript
// bad
var e = $("body");

// good
var el = $(" body");
```

## Loops

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
