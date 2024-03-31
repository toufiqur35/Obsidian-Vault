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