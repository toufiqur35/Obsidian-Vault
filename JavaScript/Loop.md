* for in loop use object
```js
 var persion ={
	name:'sobuj',
	age:24,
	city:'bogura'
}
 for(let props in persion)
 {
 document.write(props+"<br/>") //key
 document.write(persion[props]+"<br/>") //value
 document.write(props + ":" + persion[props]+"<br/>") //key and value
 }
```

* for of loop use array
```js
var cityList =['bogura','dhaka','sirajgang']

for(let city of cityList)
 {
 document.write(city+"<br/>")
 }
```
