PHP function is a piece of code that can be reused many times. It can take input as argument list and return value. There are thousands of built-in functions in PHP.

In PHP, we can define **Conditional function**, **Function within Function** and **Recursive function** also.
```php
function sayHello(){  
echo "Hello PHP Function";  
}  
sayHello();//calling function

function isEven($n)
{
if($n % 2 == 0)
	{
		return true;
	}
		return false;
	}
	$x = 13;
	if(isEven($x))
	{
		echo "{$x} is an event number";
	}
	else{
		echo "{$x} is an odd number";
	}
```

Built-in Functions: 
These are the standard functions that are always available in PHP without any special requirement like. strlen(): To get the length of a string. array_merge(): To merge two or more arrays. is_numeric(): To check if a variable is a number or a numeric string. Build In Functions List https://www.php.net/manual/en/indexes.functions.php 
```php
$string = "Hello,World!"; 
$length = strlen($string); 
echo $length; 
$value="12Z"; 
if (is_numeric($value)) { 
echo "The value '$value' is numeric"; 
} 
else { 
echo "The value '$value' is NOT numeric"; 
}
```
User-defined Functions: 
These are functions created by the programmer. They're defined using the function keyword.