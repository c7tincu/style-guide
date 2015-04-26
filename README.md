Front-End Development Style Guide
=================================



## Table of Contents

1. [JS](#js)
  1. [Types](#types)
  * [Objects](#objects)
  * [Arrays](#arrays)
* [CSS](#css)



## JS

This JS Style Guide is based on [Airbnb’s](https://github.com/airbnb/javascript) (as of late April 2015), but it aims to be more thorough. Also, where my opinions are considerably different from (or even opposed to) the given reference, a “:warning:” icon indicates that. Moreover, a “:lipstick:” icon indicates cosmetical preferences.



### Types

:boom: There are six primitive types in JS: _Boolean_, _Number_, _String_, _Null_, _Undefined_ & _Symbol_ (new in ES6), and a complex one: _Object_, that includes _Arrays_, _Functions_, _RegExps_, _Dates_, etc. When referring to them (e.g. in JSDoc), use _PascalCase_.



### Objects

:boom: Use the literal syntax to create _Objects_:

```javascript
// GOOD:
var foo = {};

// BAD:
var foo = new Object();
```

:boom: :warning: Don’t strive to avoid reserved words for _Object_ keys. There’s no need to do that. Just place them inside quotes, like this: `{ 'class': 'ns-Block-element' }`, or like this: `$el['class'] = 'ns-Block-element'`, if needed.

:boom: :lipstick: For empty & one-property _Object_ literals, use one line of code. Otherwise, split lines:

```javascript
var foo = {};
var bar = { baz: 'foo' }; // Note the spaces inside the curly braces.
var someObject = {
  foo: 'bar',
  baz: true
};
```




### Arrays

:boom: Use the literal syntax to create _Arrays_:

```javascript
// GOOD:
var foo = [];

// BAD:
var foo = new Array();
```

:boom: Use `Array#push()` to append elements to an _Array_:

```javascript
// GOOD:
foo.push('bar');

// BAD:
foo[foo.length] = 'bar';
```

:boom: To copy an _Array_, use `Array#slice()`:

```javascript
// GOOD:
var fooCopy = foo.slice();

// BAD:
var fooCopy = [];
for (var index = 0, length = foo.length; index < length; ++index) {
  fooCopy[index] = foo[index];
}
```

:boom: To convert an _Array_-like _Object_ (e.g. _Arguments_) to an _Array_, also use `Array#slice()`:

```javascript
var someFunction = () => {
  var args = Array.prototype.slice.call(arguments);
};
```

:boom: :lipstick: For zero-length & one-element _Array_ literals, use one line of code. Otherwise, split lines:

```javascript
var foo = [];
var bar = [ 'baz' ];
var someArray = [
  'foo',
  'bar',
  'baz'
];
```

:boom: :lipstick: Write `foo[index]` (without spaces inside the square brackets) for property accessors, just like for _Objects_. But write `var foo = [ 'bar' ];` (with spaces) for the literal _Array_ syntax.

:boom: Don’t leave a trailing comma after an _Array_’s last element:

```javascript
// GOOD:
var someArray = [
  'foo',
  'bar'
];

// BAD:
var someArray = [
  'foo',
  'bar',
];
```


## CSS
