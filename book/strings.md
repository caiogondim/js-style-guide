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
