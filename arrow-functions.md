# Arrow functions
Arrow functions are the new syntax for function declarations. Unlike pre-ES6 functions, they do not bind this when the functions is being defined rather when it is being called and don’t require a return keyword

## Syntax Changes
```js
  function add (x, y) {
    return x + y
  }
```

Using ES6 this would now look like this.
```js
const add = (x, y) => x + y
```
Since arrow functions are anonymous we typically assign it with const unless we need to reassign it later , in which case we would use let.

### Single Line Expressions

```js
function addTwo (x) {
  return x + 2
}

var arr = [1, 2, 3];

function mapArr = arr.map(function (item) {
  return item + 1
});

```

Using ES6 we can write these function on one line, like so

```js
const addTwo = (x => x + 2);

const arr = [1, 2, 3];

mapArr = arr.map(item => item + 1));
```

We can remove the brackets around the argument when the expression is on one line. Syntax sugar FTW!

## This
Using arrow functions has implications depending on its execution context with regard to `this`

In ES5 we would use `Function.prototype.bind(this)` to change the value of this when the function is being called as ES5 function declaration binds this when the function is being defined.

```js

function Person (name) {
  this.name = name
 	setInterval(function sayHello() {
    console.log('Hello'  + this.name)
  }, 1000);
}

var person = new Person();
// Hello
// we only log 'Hello' as this refers to the sayHello function and not to Person function, therefore this.name has not been declared

function Person (name) {
  this.name = name;

  setInterval(function sayHello() {
    console.log('Hello '  + this.name)
  }.bind(this), 1000);
}

var person = new Person ('John');
// Hello John

// Now we have bound the variable this from the Person function to the say Hello function we can access this.name

```

In ES6 we can simplify this using arrow functions as they bind this to wherever the function is being called.
```js

function Person (name) {
  this.name = name;
  setInterval(() => console.log(`Hello ${this.name}`));
}

const person = new Person ('John') ;

// Hello John
```

If we ever need to inject this into a function on execution we can not use an arrow function as we are unable to reassign this. Therefore we have to fallback to our ES5 syntax in this scenario.

## TLDR

Arrow functions are shorter syntax for function declarations and do not bind this.
