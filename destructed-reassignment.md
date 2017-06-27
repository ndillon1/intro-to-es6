# Destructured reassignment

This is an ES6 feature that allows us to extract properties from an object using an object pattern.

```js
const obj = { a: 1, b: 2 }

let { a, b } = obj;

console.log(a); // 1
console.log(b); // 2

const arr = [1, 2, 3]

[x, y, z]  = arr;

console.log(x); // 1
console.log(y); // 2
console.log(z); // 3

```
