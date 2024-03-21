* The JavaScript date object can be used to get year, month and day.
#### getDate()
* It returns the integer value between 1 and 31 that represents the day for the specified date on the basis of local time. 
```js
var myDate = new Date();
var result = myDate.getDate();
document.write(result);   //           output: 21
```
#### getDay()
* It returns the integer value between 0 and 6 that represents the day of the week on the basis of local time. 
```js
var myDate = new Date();
var result = myDate.getDay();
document.write(result);   //           output: 4
```
#### getFullYears() 
* It returns the integer value that represents the year on the basis of local time. 
```js
var myDate = new Date();
var result = myDate.getFullYears();
document.write(result);      //           output: 2024
```
#### getHours() 
* It returns the integer value between 0 and 23 that represents the hours on the basis of local time. get
```js
var myDate = new Date();
var result = myDate.getHours();
document.write(result);      //           output: 16
```
#### Milliseconds()
* It returns the integer value between 0 and 999 that represents the milliseconds on the basis of local time.
```js
var myDate = new Date();
var result = myDate.Milliseconds();
document.write(result);      //           output: 270
```

#### getMinutes()
* It returns the integer value between 0 and 59 that represents the minutes on the basis of local time. 
```js
var myDate = new Date();
var result = myDate.Milliseconds();
document.write(result);      //           output: 35
```
#### getMonth()
* It returns the integer value between 0 and 11 that represents the month on the basis of local time. 
```js
var myDate = new Date();
var result = myDate.Milliseconds();
document.write(result);      //           output: 2
```
#### getSeconds() 
* It returns the integer value between 0 and 60 that represents the seconds on the basis of local time.
```js
var myDate = new Date();
var result = myDate.Milliseconds();
document.write(result);      //           output: 45
```

#### getUTCDate() 
* It returns the integer value between 1 and 31 that represents the day for the specified date on the basis of universal time. 
```js
var myDate = new Date();
var result = myDate.getUTCDate();
document.write(result);      //           output: 21
```
#### getUTCDay() 
* It returns the integer value between 0 and 6 that represents the day of the week on the basis of universal time. 
```js
var myDate = new Date();
var result = myDate.getUTCDay();
document.write(result);      //           output: 2
```
#### getUTCFullYears() 
* It returns the integer value that represents the year on the basis of universal time. 
```js
var myDate = new Date();
var result = myDate.getUTCFullYears();
document.write(result);      //           output: 2024
```
#### getUTCHours() 
* It returns the integer value between 0 and 23 that represents the hours on the basis of universal time. 
```js
var myDate = new Date();
var result = myDate.getUTCHours();
document.write(result);      //           output: 6
```
#### getUTCMinutes() 
* It returns the integer value between 0 and 59 that represents the minutes on the basis of universal time. 
```js
var myDate = new Date();
var result = myDate.getUTCMinutes();
document.write(result);      //           output: 55
```
#### getUTCMonth() 
* It returns the integer value between 0 and 11 that represents the month on the basis of universal time.
```js
var myDate = new Date();
var result = myDate.getUTCMonth();
document.write(result);      //           output: 3
```