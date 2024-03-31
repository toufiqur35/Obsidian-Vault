* Classes are blueprints of an Object 
* Class is a template while Objects are instances of the class 
* Using let or var to declare variables inside a class is unnecessary because class properties are automatically scoped to the class instance and don't require explicit variable declarations

```js
class Person { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) } 
} 
const person1 = new Person(); 
console.log(person1.getName());

//OutPut:
//The name of the person is Jhon Dee
```

#### Re-declaring Class 
* A class can be declared once only. If we try to declare class more than one time, it throws an error.
```js
class Person { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) } 
} 
const person1 = new Person(); 
console.log(person1.getName()); 

//Re-declaring Class 
class Person{ 
}

//OutPut:
// Identifier 'Person' has already been declared
```

#### Another way to define a class is by using a class expression. 
* Here, it is not mandatory to assign the name of the class. 
* So, the class expression can be named or unnamed
```js
// normal class
let Person=class { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) 
} 
}
const person1 = new Person(); 
console.log(person1.getName()); 


// class expression
let Person=class American { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) } 
}
const person1 = new Person(); 
console.log(person1.getName())

//OutPut:
// The name of the person is Jhon Dee
```

#### Re-declaring Class 
* In this way you can redeclare class
```js
var Person=class { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) }
} 
const person1 = new Person(); 
console.log(person1.getName()); 

//Re-declaring Class 
var Person=class { 
//Properties 
first_name='Toufiqur' 
last_name='Sobuj' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) } 
} 
const person2 = new Person(); // main change
console.log(person2.getName());

//OutPut:
// The name of the person is Toufiqur Sobuj
```