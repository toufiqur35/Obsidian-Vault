#### JavaScript Object An Object is a unique entity that contains properties like. 
* Variable type properties 
* Method properties
* Object properties 
* Array properties
#### There are 3 ways to create objects. 
*  By object literal 
```js
let person = { 
//Properties 
first_name: 'Jhon', 
last_name: 'Dee', 
//method 
getName:()=> { 
return (`The name of the person is ${person.first_name} ${person.last_name}`) } 
} 
console.log(person.getName());
```

*  By creating instance of Object 
```js
var person=new Object(); 
person.first_name= 'Jhon'; 
person.last_name= 'Dee'; 
person.getName=()=> { 
return (`The name of the person is ${person.first_name} ${person.last_name}`)
} 
console.log(person.getName());
```

*  By using an Object constructor 
```js
function Person() { 
this.first_name = 'Jhon'; 
this.last_name = 'Dee'; 
this.getName = function() { 
return `The name of the person is ${this.first_name} ${this.last_name}`}; 
} 
var person = new Person(); 
console.log(person.getName());
```