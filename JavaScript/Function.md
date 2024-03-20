#### Name functions its parameters & return


```js
var x= 5;
var y= 7;
function addToNumber()
{
  var r = x+y;
  document.write(r);
}
addToNumber();
```

* parameter function
```js
function addToNumber(a,b)
{
  var x = a;
  var y = b;
  var r = x+y;
  document.write(r);
}
addToNumber(4,6);
```


* return function
```js
function myFun()
{
  var x = 5;
  var y = 6;
  return x+y;
}
document.write(myFun());

function myFun2(a,b)
{
  return a+b;
}
document.write(myFun2(15, 6));
```

* Anonymous function
* j function ar name na thaka
```js
const name = function(n)
{
alert("name"+n)
}
name("sobuj")
```


* Arrow function
```js
const name =>(n)
{
alert("name"+n)
}
name("sobuj")
```