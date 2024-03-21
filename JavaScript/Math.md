* The JavaScript math object provides several constants and methods to perform mathematical operation.
#### abs() 
* It returns the absolute value of the given number. 
```js
let a = Math.abs(7.25);
let b = Math.abs(-7.25);
let c = Math.abs(null);
let d = Math.abs("Hello");
let e = Math.abs(2 - 3);

document.write(a);    // output: 7.25  
document.write(b);    // output:  7.25 
document.write(c);    // output:  0
document.write(d);    // output:  NaN
document.write(e);    // output:  1
```
#### ceil() 
* It returns a smallest integer value, greater than or equal to the given number. 
```js
let a = Math.ceil(0.60);
let b = Math.ceil(0.40);
let c = Math.ceil(5);
let d = Math.ceil(5.1);
let e = Math.ceil(-5.1);

document.write(a);    // output: 1 
document.write(b);    // output:  1 
document.write(c);    // output:  5
document.write(d);    // output:  6
document.write(e);    // output:  -5
```
#### floor()
* It returns largest integer value, lower than or equal to the given number. 
```js
let a = Math.ceil(0.60);
let b = Math.ceil(0.40);
let c = Math.ceil(5);
let d = Math.ceil(5.1);
let e = Math.ceil(-5.1);

document.write(a);    // output: 0
document.write(b);    // output:  0 
document.write(c);    // output:  5
document.write(d);    // output:  5
document.write(e);    // output:  -6
```
#### max() 
* It returns maximum value of the given numbers. 
```js

```
#### min() 
* It returns minimum value of the given numbers. 
```js

```
#### random() 
* It returns random number between 0 (inclusive) and 1 (exclusive). 
```js

```
#### round() 
* It returns closest integer value of the given number.
```js

```