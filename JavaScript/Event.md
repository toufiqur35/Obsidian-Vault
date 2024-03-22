#### COMMON JAVASCRIPT EVENTS
#### onclick() 
* The user clicks an HTML element 
```js
<button onclick="MyEvent('click hoica')">click</button>

function MyEvent(msg) {
	document.write(msg);
}
```
#### onchange() 
* An HTML element has been changed
```js
<button onchange="MyEvent('onchange hoica')">click</button>

function MyEvent(msg) {
	document.write(msg);
}
```
#### onmouseover() 
* The user moves the mouse over an HTML element 
```js

<button onmouseover="MyEvent('onmouseover hoica')">click</button>

function MyEvent(msg) {
	document.write(msg);
}
```
#### onmouseout() 
* The user moves the mouse away from an HTML element 
```js

<button onmouseout="MyEvent('onmouseout hoica')">click</button>

function MyEvent(msg) {
	document.write(msg);
}
```
#### onkeydown() 
* The user pushes a keyboard key onload() The browser has finished loading the page
```js
<button onkeydown="MyEvent('onkeydown hoica')">click</button>
function MyEvent(msg) {
	document.write(msg);
}
```