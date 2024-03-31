#### Class constructor is a magic method 
 * Constructor execute automatically when object is created 
 * Constructor can take parameter 
 * Constructor method can't return any result
```js
class Person { 
constructor() { 
console.log('I am a constructor') 
} 
} 
new Person();

//OutPut:
// I am a constructor
```

#### Constructor Parameter
```js
class Person { 
constructor(msg) { 
console.log(msg) 
} } 
const person1 = new Person('I am a constructor');

//OutPut:
// I am a constructor
```

#### Change class properties value using constructor
```js
var Person=class { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
constructor(name1,name2) { 
this.first_name=name1 
this.last_name=name2 
} 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) 
} }
const person1 = new Person("toufiqur","sobuj"); 
console.log(person1.getName());

//OutPut:
// The name of the person is toufiqur sobuj
```