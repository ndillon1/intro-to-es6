# Template Literals
Template literals are strings allowing embedded expressions, that use backticks (``)  and ${variable} syntax.

With them we can handle dynamic variables, multi-line strings and expression interpolation features.

## Multi-Line Strings
Using template literals we can create multi-line strings like the code below

```js
const first_name = Sarah;
const last_name = Jones;

console.log(`My first name is ${first_name} and
my last name is ${last_name}`
```

Before template literals we would have to construct our string like this.
```js
var first_name = Sarah;
var last_name = Jones;
console.log('My first name is' + first_name + 'and\n my last name is' + last_name);
// My first name is Sarah and
// my last name is Jones
```

## Expression interpolation
```js
const add(x) {
	return x + 2
}

console.log(`1 plus 2 equals ${add(1}`)
// 1 plus 2 equals 3

```
