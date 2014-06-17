# Naming

## Avoid double negatives

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

## Verbal actions

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

## Mutable versus immutable methods

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
