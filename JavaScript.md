`//` hashes out code

multi line comments with `/*` and `*/`. Can also be used to comment out the middle of lines.

7 different data types in JavaScript:
* *Number*, including numbers with decimals.
* *String*, surround by single or double quotes, convention says single quotes.
* *Null*, represents the intentional absence of a value.
* *Boolean*, true or false.
* *Undefined*, represents the absence of data.
* *Symbol*, unique identifier.
* *Object*, collection of related data.

## TYPEOF

`typeof` will return the type the javascript item is. *note if item is array `typeof` will still return `'object'`*

## STRINGS
`.length` on a string prints the number of characters in that string including spaces.
`.toUpperCase()` on a string turns that string to uppercase.
`.startsWith('H')` on a string is True or False if that string begins with 'H'.
`.trim()` on a string removes all the empty spaces.

### REGULAR EXPRESSIONS

Or *RegEx*.

Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These patterns are used with the exec and test methods of RegExp, and with the match, matchAll, replace, search, and split methods of String.

[MDN Web Docs - Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)


Methods that use regular expressions:
* **exec**:	A RegExp method that executes a search for a match in a string. It returns an array of information or null on a mismatch.
* **test**:	A RegExp method that tests for a match in a string. It returns true or false.
* **match**:	A String method that returns an array containing all of the matches, including capturing groups, or null if no match is found.
* **matchAll**:	A String method that returns an iterator containing all of the matches, including capturing groups.
* **search**:	A String method that tests for a match in a string. It returns the index of the match, or -1 if the search fails.
* **replace**:	A String method that executes a search for a match in a string, and replaces the matched substring with a replacement substring.
* **split**:	A String method that uses a regular expression or a fixed string to break a string into an array of substrings.

### NUMBERS
`Math.floor(6.88)` will return 6 or round down to the nearest whole number.
`Math.random()` generates a random number between 0 and 1.
`Math.ceil(6.88)` will return 7 or round up to the nearest whole number.
`Number.isInteger(2019)` will return true and for any other integer.

### OBJECTS
`Object.keys(objectName)` will return an array of a given objects property names.

### ASYNCHRONOUS JAVASCRIPT

The `Promise` object:
* Pending: the initial state -- the operation has not yet completed.
* Fulfilled: The operation has completed successfully and the promise now has a resolved value. For example, a request’s promise might resolve with a JSON object as its value.
* Rejected: The operation has failed and the promise has a reason for the failure. This reason is usually an Error of some kind.

### VAR vs. LET vs. CONST

`var` is function scoped

`let` is block scoped

`const` is block scoped. Cannot be reassigned a new value but object attributes can be changed.

### NEW SET

Lets you store unique values of any type, whether primitive values or object references.

```js
var mySet = new Set();

mySet.add(1); // Set [ 1 ]
mySet.add(5); // Set [ 1, 5 ]
mySet.add(5); // Set [ 1, 5 ]
```

### ARRAYS

* Loop over an array:
```js
fruits.forEach(function(item, index, array) {
  console.log(item, index);
});
```

or simpler:
```js
array1.forEach(function(element) {
  console.log(element);
});
```

**slice**

Returns a shallow copy of a portion of an array into a new array object selected from begin to end (end not included) where begin and end represent the index of items in that array.

```js
var animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]
```


*CodeWars*:

```js
function accum(s) {
  return s.split('').map((c, i) => (c.toUpperCase() + c.toLowerCase().repeat(i))).join('-');
}
```

* Return unique characters in array:
```js
function longest(s1, s2) {
  return Array.from(new Set(s1 + s2)).sort().join('');
}
```

* removes all non letters and reverses:
```js
function reverseLetter(str) {
  return str.replace(/[^a-z]/gi, '').split('').reverse().join('')
}
```
or
```js
function reverseLetter(str) {
  return str.match( /[a-z]/gi ).reverse().join('')
}
```

* Tests for the number of character smiley faces in an array:
```js
function countSmileys(arr) {
  return arr.filter(x => /^[:;][-~]?[)D]$/.test(x)).length;
}
```

* Creating a mexican wave out of an array. Input/Ouput = `wave("hello") => ["Hello", "hEllo", "heLlo", "helLo", "hellO"]`:
```js
function wave(str){
    let result = [];
    
    str.split("").forEach((char, index) => {
        if (/[a-z]/.test(char)) {
            result.push(str.slice(0, index) + char.toUpperCase() + str.slice(index + 1));
        }
    });
    
    return result;
}
```