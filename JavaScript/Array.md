#### Array
* An array is a collection of items of same data type stored at contiguous memory locations.
```js
const cars = ["Saab", "Volvo", "BMW"];
```
#### array concatenate
* In order to combine (concatenate) two arrays.
```js
var a = ['A','B','C'];
var b = ['D','E','F'];
var result = a.concat(b);
document.write(result);
```
#### Array Form
* The form method create a new array that holds the shallow copy from an array or iterable object.
* when applied to a string, each word gets converted to an array element in the new array.
```js
var name = "sobuj";
var r = Array.from(name);
document.write(r);
```

#### Array filter
* The `filter()` method creates a new array filled with elements that pass a test provided by a function.
* The `filter()` method does not execute the function for empty elements.
* The `filter()` method does not change the original array.
```js
var num = [10,20,30,22,35,50];
var result = num.filter(function(item)
{
	return item<20;
})
document.write(result);

const ages = [32, 33, 16, 40];  
const result2 = ages.filter(checkAdult);  
  
function checkAdult(age) {  
  return age >= 18;  
}
document.write(resutl2);
```

#### Array Find
* The `find()` method returns the value of the first element that passes a test.
* The find() method executes a function for each array element.
* The find() method returns undefined if no elements are found.
* The find() method does not execute the function for empty elements.
* The find() method does not change the original array.
```js
//find
var num = [10,20,30,22,35,50];
var result = num.find(function(item)
{
	return item<20;
})
document.write(result);

//find Index
var num = [10,20,30,22,35,50];
var result = num.findIndex(function(item)
{
	return item<20;
})
document.write(result);
```

#### Array for Each
* The `forEach()` method calls a function and iterates over the elements of an array.
```js
//Anonymous function
var numArray = [10, 20, 30, 22, 35, 50];
numArray.forEach(function (item) {
	document.write(item + '<br/>');
});

//normal function
var numArray = [10, 20, 30, 22, 35, 50];
numArray.forEach(value);
function value(item) {
	document.write(item + '<br/>');
}
```

#### Array includes

* includes() পদ্ধতিটি সত্য দেখায় যদি একটি অ্যারেতে একটি নির্দিষ্ট মান থাকে। মান পাওয়া না গেলে includes() পদ্ধতি মিথ্যা প্রদান করে। includes() পদ্ধতিটি কেস সংবেদনশীল।
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const r = fruits.includes("Banana");
document.write(r);
```

#### Array Index Of
* The indexOf() method **searches an array for an element value and returns its position**. 
* The first item has position 0, the second item has position 1, and so on.
* The `indexOf()` method returns -1 if the value is not found.
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
let index = fruits.indexOf("Apple");
document.write(index)
```

##### Array Reverse
* The java-Script array reverse method change the sequence of element of the given array and return the reverse sequence.
```js
var numArray = [10, 20, 30, 22, 35, 50];
var resutl = numArray.reverse();
document.write(resutl);
```

##### Array Push
* The java-Script array push method adds one or more to the end of the given array and return that element.
```js
var numArray = [10, 20, 30, 22, 35, 50];
numArray.push(100,200);
document.write(numArray);
```
##### Array Pop
* The java-Script array pop method remove the last element from the given array and return that element.
```js
var numArray = [10, 20, 30, 22, 35, 50];
numArray.pop();
document.write(numArray);
```