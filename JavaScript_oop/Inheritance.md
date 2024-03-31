* Keyword extends is used to create inherit relationship between class 
* For inherit relationship child class can use parent class properties
```js
class Father { 
//Properties 
first_name='Jhon' 
last_name='Dee' 
//method 
getName() { 
return (`The name of the person is ${this.first_name} ${this.last_name}`) 
} 
} 
class Son extends Father{ 
} 
const SonObj = new Son(); 
console.log(SonObj.getName());

// OutPut:
// The name of the person is Jhon Dee
```

* Call parent class function and properties in child class
```js
class Father { 
//Properties 
first_name = 'Jhon'; 
last_name = 'Dee'; 
//method 
getName() { 
return `The name of the person is ${this.first_name} ${this.last_name}`; 
}
} 
class Son extends Father { 
getFirstName() { 
return this.getName(); 
} 
} 
const son = new Son(); 
console.log(son.getFirstName());

// OutPut:
// The name of the person is Jhon Dee
```