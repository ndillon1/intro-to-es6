# Classes
Javascript is an Object Orientated but doesn't use the same class model like Java or C#, but through using ES6 we can apply these concepts more easily using keywords class, constructor, extends,  super and get.

```js

class Person {
	constructor(first_name, last_name, age) {
		this.first_name = first_name,
		this.last_name = last_name,
		this.age = age,
	}

	sayHi() {
		console.log(`Hi ${this.first_name}`)
	} // class methods

	get nameLength() {
		return `${this.first_name}${this.last_name}`.length
	} //  attribute getter methods
}

const john = new Person('John', 'Smith', 24);

john.sayHi() // 'Hi John'

john.nameLength // 9
```

#Subclasses
To create ’subclasses’ in Javascript we use the *extend* keyword and to call the constructor method of the parent class we use the keyword *super*
```js

class Woman extends Person {
	constructor(first_name, last_name, age) {
		super(first_name, last_name, age) // call constructor methods of parent class
		this.gender = 'female'
	}
}

const sarah = new Woman('Sarah', 'Jones', 24);

sarah.sayHi() // 'Hi Sarah'

sarah.nameLength // 10

sarah.gender = 'female'

```
## Before
Without ES6 this would look like

```js

function Person(first_name, last_name, age) {
	this.first_name = first_name,
	this.last_name = last_name,
	this.age = age
}

Person.prototype = {
	sayHi: function () {
		console.log(`Hi ${this.first_name}`)
	}

	nameLength: function () {
		return `${this.first_name}${this.last_name}`.length
	}
}

var john = new Person('John', 'Smith', 24);

john.sayHi() // Hi John
console.log(john.nameLength) // undefined
console.log(john.nameLength()) //

function Woman (first_name, last_name, age) {
	Person.call(this, first_name, last_name, age)
	this.gender = 'female'
}

Woman.prototype = Object.create(Person.prototype);
// Woman class directly inherits from the person class
Woman.prototype.constructor = Woman;
// The constructor name needs to be changed from Person to
Woman

var sarah = new Woman('Sarah', 'Jones', 24);

sarah.sayHi() // Hi Sarah
sarah.gender // female

```

#intro-to-es6
