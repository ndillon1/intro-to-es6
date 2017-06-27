# Rest Parameters and Spread Operators

## Rest Parameter
The rest parameters are a part of ES6 syntax that allows us to access the arguments of a function without dealing with the arguments object.

When we use the rest parameters we assign all those arguments to one variable in the format of an array.

```js
const add = (...numbers) => numbers.reduce((a, b) => a + b);

add(1, 2, 3, 4, 5) // 15

//numbers in this example is equal to this array [1, 2, 3, 4, 5]
```

If variable assignments precede the rest parameter they will be made first. Therefore, we can also use the rest parameters like this.

```js
const multiply = (factor, ...numbers) => (numbers.map(item => item * factor)

multiply(2, 1, 2, 3, 4) // [2, 4, 6, 8]

// factor in this case is 2
// numbers is [1, 2, 3, 4]
```

The rest parameter has to be the last parameter of a function, therefore the following code will not work

```js

const rest = (...x, y) => {
	console.log(x);
}
//Syntax Error
```

## Spread Operator

The spread operator is  syntactically the same as rest parameter but they work in the opposite way. Whilst rest parameters, take parameters and turn them into a variable assigned array, spread operators take objects and turn them into seperate variables

### Function Calls
```js
const add = (x, y) => {x + y}

const arr = [1, 2]

add(...arr) // 3
```

### Array manipulation
```js
const animals = ['Bear', 'Tiger'];  
const otherAnimals = ['Lion', 'Monkey'];
animals.push.apply(countries, otherCountries) // ['Bear', 'Tiger', 'Lion', 'Monkey']

// ES6
animals.push(...otherAnimals)
```

### Array Concatenation
```js
const allAnimals = animals.concat(otherAnimals)

// ES6
const allAnimals = [...animals, ...otherAnimals]
```

### Array Cloning
```js
const clonedAnimals = [...animals]
console.log(clonedAnimals === animals) // false
```

### Destructuring assignments
```js
const arr = [1, 2, 3, 4, 5]
const [first, ...middle, last] = arr;

console.log(first); // 1
console.log(middle); // [2, 3, 4]
console.log(last); // 5
```

### Object Cloning
```js
const obj = { a: 1, b: 2 }
const newObj = Object.assign({}, obj)

// ES6
const newObj = {...obj}
```

### Object Merging
```js
const obj = { a: 1, b: 2 }
const otherObj = { c: 3 }

const newObj = Object.assign({}, obj, otherObj)

//ES6
const newObj = {...obj, ...otherObj}
```
