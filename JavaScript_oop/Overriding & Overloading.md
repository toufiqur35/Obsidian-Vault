 * Overriding works for inheritance relationship 
 * When child class change his parent properties , that is overriding 
 
 ```js
 class Father { 
 first_name='Jhon' 
 last_name='Dee' 
 getName() {
  return (`The name of the person is ${this.first_name} ${this.last_name}`) 
  } 
  } 
  class Son extends Father{ 
  first_name='Jhon Junior' 
  } 
  const SonObj = new Son(); 
  console.log(SonObj.getName());

// OutPut:
// The name of the person is Jhon Junior Dee
```

#### Method Overloading 
* Object-oriented languages like Java or C++, method overloading allows a class to have multiple methods with the same name but different parameters. 
* However, in JavaScript, there's no direct support for method overloading in the traditional sense. 
* Yet, you can simulate method overloading by examining the number of arguments passed and then deciding how to handle them within the function. 

```js
class MyClass { 
myMethod(param1, param2) { 
if (arguments.length === 1) {
console.log('Received one argument:', param1); 
} 
else if (arguments.length === 2) { 
console.log('Received two arguments:', param1, param2);
} 
else { 
console.log('Invalid number of arguments'); 
} 
} 
} 
const obj = new MyClass(); 
obj.myMethod(10); 
obj.myMethod(20, 30* 

// OutPut:
// Received one argument: 10
// Received two arguments: 20 30
```