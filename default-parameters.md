# Default parameters
We can set default parameters to functions if we don’t provide any.

```js
const sayHello (name = 'John') {
	return `Hello ${name}`;
}

console.log(sayHello()); // Hello John
console.log(sayHello(Sarah)); // Hello Sarah
```

Before ES6 we would have to write our code like this

```js
function sayHello (name) {
	var name = name || 'John'
	return 'Hello' + name;
}

console.log(sayHello()); // Hello John
console.log(sayHello(Sarah)); // Hello Sarah
```
