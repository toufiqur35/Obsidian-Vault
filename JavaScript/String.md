#### charAt()
* The JavaScript string charAt() method is used to find out a char value present at the specified index in a string.
```js
var country = "Bangladesh"
var result = country.charAt(3);
document.write(result);  //               output: g 
```

#### concat()
* It provides a combination or join of two or more strings.
```js
var country = "Dhaka"
var country2 = "Bogura"
var result = country.concat(country2);
document.write(result);  //               output: DhakaBogura 
```

#### indexOf() 
* It provides the position of a char value present in the given string. 
```js
var country = "Bangladesh"
var result = country.indexOf("l");
document.write(result);    //               output: 4 
```
##### lastIndexOf() 
* It provides the position of a char value present in the given string by searching a character from the last position.
```js
var country = "Bangladesh bogura"
var result = country.lastIndexOf('bogura');   // full/single string ex: ("bogura"or"u")
document.write(result);     //               output: 11
```
#### replace() 
* It replaces a given string with the specified replacement. 
```js
//syntex: var result = country2.replace('main text','new/replace text'); 
var country2 = "Dhaka"
var result = country2.replace('Dhaka','bogura');
document.write(result);  //               output: bogura
```
#### substr() 
* It is used to fetch the part of the given string on the basis of the specified starting position and length.
```js
//syntex: var result = country.substr(index number, length); 
var country = "Bangladesh"
var result = country.substr(1,4);
document.write(result);  //               output: angl
```

#### substring() 
* It is used to fetch the part of the given string on the basis of the specified index.
```js
//syntex: var result = country.substr(index number, 0 index to length); 
var country = "Bangladesh"
var result = country.substring(1,4);
document.write(result);  //               output: angl
```
#### slice() 
* It is used to fetch the part of the given string. It allows us to assign positive as well negative index.
```js

```
#### toLowerCase() 
* It converts the given string into lowercase letter.
```js

```
#### toUpperCase() 
* It converts the given string into uppercase letter. 
```js

```
#### trim() 
* It trims the white space from the left and right side of the string.
```js

```