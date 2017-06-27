# Let and Const Variable Declarations
Previous to ES6 we use var to create variable declarations. The differences between var, let and const lies in variable declarations and value assignment.

## Var vs Let
The difference between var and let is that var variables can be accessed by the global or functional scope where as let can only be accessed by the block in which it has been defined.


```js
var x = 2;

function add () {
  for (let i = 0; i < 5; i++) {
    x+=i
    console.log(i);
  }
}

add();
// We can log i within the for loop it has been defined in since let variables can be accessed inside their block scope
	// 0
	// 1
	// 2
	// 3
	// 4

console.log(x); // 12 --> x is defined in the global scope so we can access it outside the function
console.log(i) // undefined --> since we are outside i's block scope we can not access it
```

## Let vs Const
Like let , const variable declarations can only be accessed within the same block scope. However const variables can not be reassigned to another reference and can not be redeclared.

```js

let x = 2;

x = { a : 1 }

console.log(x)  // { a: 1}
const arr  = [1, 2, 3];

arr = [4, 5, 6] // this would not work as we are trying to assign the constant arr variable to a new reference. A runtime error would occur at this point.

arr.push(4)

console.log(arr) --> [1, 2, 3, 4]

```

## TLDR;
Read it! 🤣

.....

Just kidding . . . . Let and const can only be accessed within the block that they have been defined in and const variables can not be reassigned to the value of another reference!
