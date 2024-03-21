```js
var appCodeName = navigator.appCodeName;
var appName = navigator.appName;
var appVersion = navigator.appVersion;
var cookieEnabled = navigator.cookieEnabled;
var language = navigator.language;
var userAgent = navigator.userAgent;
var platform = navigator.platform;
var onLine = navigator.onLine;

document.write(appCodeName+"<br/>"); // output: mozilla
document.write(appName+"<br/>"); // output: Netscape
document.write(appVersion+"<br/>"); // output: 5.0 (Windows)
document.write(cookieEnabled+"<br/>"); // output: true
document.write(language+"<br/>"); // output: en-US
document.write(userAgent+"<br/>"); // output: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101
document.write(platform+"<br/>"); // output: Firefox/124.0
document.write(onLine+"<br/>"); // output: Win32
```


#### Geolocation

```js
navigator.geolocation.getCurrentPosition(function(position)

    {

	let altitude = position.coords.altitude;
	let latitude = position.coords.latitude;
	let longitude = position.coords.longitude;
	let speed = position.coords.speed;

	document.write(altitude+"<br/>"); // output: mozilla
	document.write(latitude+"<br/>"); // output: mozilla
	document.write(longitude+"<br/>"); // output: mozilla
	document.write(speed+"<br/>"); // output: mozilla

    })
```