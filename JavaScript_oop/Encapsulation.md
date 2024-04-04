* Grouping Data & Actions Encapsulation bundles data (variables) and methods (functions) together within an object. 
* Hides Complexity It hides the inner workings, allowing interaction only through a set of well-defined methods 
* Data Protection Protects data from direct access or modification from outside the object 
* Controlled Access Enables controlled access to the data, ensuring it's only changed in expected ways. 
* Enhances Maintainability Encapsulation makes code more manageable by organizing related functionalities and protecting internal data

#### Encapsulation Using Closures

```js
function createCounter() { 
let count = 0; 
return { 
increment: function() {
count++; 
}, 
getCount: function() { 
return count; 
} 
}; 
} 
const counter = createCounter(); 
counter.increment(); 
console.log(counter.getCount()); 
console.log(counter.count);


// Output:
// 1
// undefined (count is encapsulated)
```

#### Using Constructor Functions

```js
function Car(make, model) { 
let mileage = 0;
this.getMake = function() { 
return make; 
}; 
this.getModel = function() { 
return model; 
}; 
this.getMileage = function() { 
return mileage; 
}; 
this.drive = function(distance) {
mileage += distance; 
}; 
} 
const myCar = new Car('Toyota', 'Corolla'); 
console.log(myCar.getMake()); 
console.log(myCar.getMileage());
console.log(myCar.getMileage()); 
console.log(myCar.mileage); 

// Output:
// Toyota Using ES6 Classes #JavaScript_OOP
// 0 myCar.drive(100);
// 100 
// undefined (mileage is encapsulated)
```

#### Using ES6 Classes
```js

```