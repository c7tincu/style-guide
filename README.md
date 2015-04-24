Front-End Development Style Guide
=================================



## Table of Contents

1. [JS](#js)
  1. [Types](#types)
  * [Objects](#objects)
  * [Arrays](#arrays)



* [CSS](#css)



## JS

### Types

* There are six primitive types in JS: _Boolean_, _Number_, _String_, _Null_, _Undefined_, _Symbol_ (new in ES6), and a complex type: _Object_, that includes _Array_, _Function_, _RegExp_, _Date_, etc. When referring to them (e.g. in JSDoc), we use uppercase.



### Objects

* We use the literal syntax to create _Objects_:

:+1:
```javascript
var foo = {};
```
:-1:
```javascript
var foo = new Object();
```

* There’s no need for us to avoid reserved words for _Object_ keys.

* For empty & one-property _Object_ literals, we use one line. Otherwise, we split lines:

```javascript
var foo = {};
var bar = { baz: 'foo' }; // Note the spaces inside the curly braces.
var someObject = {
  foo: 'bar',
  baz: true
};
```




### Arrays

* We use the literal syntax to create _Arrays_:

:+1:
```javascript
var foo = [];
```
:-1:
```javascript
var foo = new Array();
```

* We use `Array#push()` to add items to an _Array_:

:+1:
```javascript
foo.push('bar');
```
:-1:
```javascript
foo[foo.length] = 'bar';
```

* To copy an _Array_, we use `Array#slice()`:

:+1:
```javascript
var fooCopy = foo.slice();
```
:-1:
```javascript
var fooCopy = [];
for (var index = 0, length = foo.length; index < length; ++index) {
  fooCopy[index] = foo[index];
}
```

* To convert an _Array_-like _Object_ (e.g. _Arguments_) to an _Array_, we also use `Array#slice()`:

```javascript
var someFunction = () => {
  var args = Array.prototype.slice.call(arguments);  
}
```

* For zero-length & one-element _Array_ literals, we use one line. Otherwise, we split lines:

```javascript
var foo = [];
var bar = [ 'baz' ];
var someArray = [
  'foo',
  'bar',
  'baz'
];
```

* We use `foo[index]` (without spaces inside the square brackets) for property accessors, just like for _Objects_. But we write `var foo = [ 'bar' ];` (with spaces) for the literal _Array_ syntax.

* We don’t allow trailing commas for arrays:

:+1:
```javascript
var someArray = [
  'foo',
  'bar'
];
```
:-1:
```javascript
var someArray = [
  'foo',
  'bar',
];
```


## CSS
