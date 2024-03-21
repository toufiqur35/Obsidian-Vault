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
let a = Math.max(5, 10);
let b = Math.max(0, 150, 30, 20, 38);
let c = Math.max(-5, 10);
let d = Math.max(-5, -10);
let e = Math.max(1.5, 2.5);

document.write(a);    // output: 10
document.write(b);    // output:  150 
document.write(c);    // output:  10
document.write(d);    // output:  -5
document.write(e);    // output:  2.5
```
#### min() 
* It returns minimum value of the given numbers. 
```js
let a = Math.min(5, 10);
let b = Math.min(0, 150, 30, 20, 38);
let c = Math.min(-5, 10);
let d = Math.min(-5, -10);
let e = Math.min(1.5, 2.5);

document.write(a);    // output: 5
document.write(b);    // output:  0
document.write(c);    // output:  -5
document.write(d);    // output:  -10
document.write(e);    // output:  1.5
```
#### random() 
* It returns random number between 0 (inclusive) and 1 (exclusive). 
```js
let x = Math.random() * 100;
let y = Math.floor((Math.random() * 100) + 1);
document.write(x);    
document.write(y);   
```
#### round() 
* It returns closest integer value of the given number.
```js
let a = Math.round(2.60);
let b = Math.round(2.50);
let c = Math.round(2.49);
let d = Math.round(-2.60);
let e = Math.round(-2.50);

document.write(a);    // output: 3
document.write(b);    // output:  3
document.write(c);    // output:  2
document.write(d);    // output:  -3
document.write(e);    // output:  -2
```

#### JAVASCRIPT NUMBER OBJECT 
* The JavaScript number object enables you to represent a numeric value. It may be integer or floating-point. 
#### isFinite()
* It determines whether the given value is a finite number.
```js
let result = isFinite(123);
document.write(e);    // output:  true
```
#### isInteger() 
* It determines whether the given value is an integer.
```js
Number.isInteger(123);  // output:  true
Number.isInteger(-123);  // output:  true
Number.isInteger('123');  // output:  false
```
#### parseFloat() 
* It converts the given string into a floating point number. 
```js
a = Number.parseFloat(10);
b = Number.parseFloat("10");
c = Number.parseFloat("10.33");
d = Number.parseFloat("34 45 66");
e = Number.parseFloat("He was 40");

document.write(a); // output: 10
document.write(b); // output:  10
document.write(c); // output:  10.33
document.write(d); // output:  34
document.write(e); // output:  NaN
```
#### parseInt() 
* It converts the given string into an integer number. 
* The `Number.parseInt` method parses a value as a string and returns the first integer.
```js
a = Number.parseInt("10");  
b = Number.parseInt("10.00");  
c = Number.parseInt("10.33");  
d = Number.parseInt("34 45 66");   
e = Number.parseInt("40 years");  
f = Number.parseInt("He was 40");

document.write(a); // output: 10
document.write(b); // output:  10
document.write(c); // output:  10
document.write(d); // output:  34
document.write(e); // output:  40
document.write(e); // output:  NaN
```
#### toFixed() 
* It returns the string that represents a number with exact digits after a decimal point. 
* The `toFixed()` method converts a number to a string.
* The `toFixed()` method rounds the string to a specified number of decimals.
```js
let num = 5.56789;
let n = num.toFixed();
document.write(n); // output:  6

let num2 = 5.56789;
let m = num2.toFixed(2);
document.write(m); // output:  5.57
```
#### toString() 
* It returns the given number in the form of string. 
```js
let num2 = 15;  
let text = num.toString();
document.write(text); // output:  15

//binary
let num2 = 15;  
let text2 = num2.toString(2);
document.write(text2); // output:  1111
```

---
####  WINDOW OBJECT 
* The window object represents a window in browser. An object of window is created automatically by the browser.
#### alert() 
* displays the alert box containing message with ok button. 
```js
alert("Hello! I am an alert box!!");
```
#### confirm() 
* displays the confirm dialog box containing message with ok and cancel button. 
```js
confirm("Press a button!");
```

#### close() 
* closes the current window. 
```js
let myWindow;  
  
function openWin() {  
  myWindow = window.open("", "myWindow", "width=200, height=100");  
}  
  
function closeWin() {  
  myWindow.close();  
}
```
#### setTimeout() 
* performs action after specified time like calling function, evaluating expressions etc.
```js
const myTimeout = setTimeout(myGreeting, 5000);

function myGreeting() {
  document.getElementById("demo").innerHTML = "Happy Birthday!"
```