#### Getter and Setter Methods 
* In JavaScript, getter and setter methods are used to control access to object properties 
* They allow you to define custom behavior when getting and setting a property
```js
class Product { 
constructor(price) { 
this.price = price; 
} //Getter for price 
get GetPrice() { 
return this.price; 
} // Setter for price 
set SetPrice(value) { 
this.price = value; 
} } 
const product = new Product(20); 
console.log(product.GetPrice); 
product.SetPrice = 25; // Setting the price using the Setter
console.log(product.GetPrice); // Getting the price using the Getter

// OutPut:
// 20
// 25
```


```js
class Triangle { 
constructor(Base,Height) { 
this.Base = Base; 
this.Height = Height; 
} 
// Setter 
set SetBase(Base) { 
this.Base = Base; 
} 
set SetHeight(Height) { 
this.Height = Height; 
} 
get GetArea(){ 
return 0.5*this.Base* this.Height; 
} 
} 
const triangle = new Triangle(20,40); 
console.log(triangle.GetArea) //Set New Base & Height triangle.SetBase=25;
triangle.SetHeight=45;
console.log(triangle.GetArea)

// OutPut:
// 400
// 450
```