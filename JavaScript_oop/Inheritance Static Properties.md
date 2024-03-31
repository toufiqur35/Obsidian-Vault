* When a class extends another, it inherits the parent class's static properties and methods 
```js
class Parent { 
static greetParent() {
return 'Hello, I am the parent!';
} 
} 

class Child extends Parent { 
static greetChild() { 
return 'Hello, I am the child!'; 
} 
} 
console.log(Parent.greetParent()); 
console.log(Child.greetParent()); 
console.log(Child.greetChild());


// OutPut:
// Hello, I am the parent!
// Hello, I am the parent!   
// Hello, I am the child!
```