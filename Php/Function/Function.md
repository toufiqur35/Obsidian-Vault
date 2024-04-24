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

#### Built-in Functions: 
These are the standard functions that are always available in PHP without any special requirement like. `strlen()`: To get the length of a string. `array_merge()`: To merge two or more arrays. `is_numeric()`: To check if a variable is a number or a numeric string. 
Build In Functions List https://www.php.net/manual/en/indexes.functions.php 
```php
$string = "Hello,World!"; 
$length = strlen($string)."\n"; 
echo $length; 
$value="12Z"; 
if (is_numeric($value)) { 
echo "The value '$value' is numeric"; 
} 
else { 
echo "The value '$value' is NOT numeric"; 
}
```
#### User-defined Functions: 
These are functions created by the programmer. They're defined using the function keyword.
```php
function sum() { 
$num1=20; 
$num2=30; 
echo $num1+$num2; 
} 
sum();
```

#### Function With Parameters
```php
function sum($num1, $num2) { 
echo $num1+$num2;
} 
sum(1,2);
```

#### Function With Parameters Default Value 
One without a default value must be declared before the one with a default value.
```php
function sum($num1, $num2=10) { 
echo $num1+$num2;
} 
sum(2);

//example 2
function serve($foodType,$numberOfItem)
{
	 echo "{$numberOfItem} of {$foodType} has been serve";
}
$ft = "coffee";
$n = "2 cups";
serve($ft,$n);

//Default value of function
function serve($foodType,$numberOfItem="1 cups")
{
	echo "{$numberOfItem} of {$foodType} has been serve";
}
$ft = "coffee";
serve($ft);
```
#### Type hinting or type checking of function parameters
**Primitive types:** like `int, float, bool, string`. 
**Classes and interfaces:** Any class or interface name. 
**Arrays:** with the array keyword.
**Callable:** for functions or objects that implement the invoke method. 
**Nullable types:** by prefixing with a ?.
**Iterables:** with the iterable keyword, which includes both arrays and objects implementing the Traversable interface. 
**Union types:** introduced in PHP 8, where a parameter can accept multiple types.
```php
//example 1
function sum(int $num1,int $num2) { 
echo $num1+$num2; 
}
sum(20,20);

//example 1
function factorial(int $n) //int type hinting
{
	$result = 1;
	for($i=$n;$i>1;$i--)
	{
		$result *= $i;
	}
	return $result;
}
$x= 4;
echo "Factorial {$x} is :".factorial($x);
//another way
function factorial($n)
{
	if(gettype($n)!="integer")// type hinting
	{
	return "invalid";
	}
		 $result = 1;
	for($i=$n;$i>1;$i--)
	{
		$result *= $i;
	}
	return $result;
}
$x= "4";
echo "Factorial {$x} is :".factorial($x);
```
Multiple type hinting in one parameter
```php
function sum(int|string $num1,int|string $num2) 
{ 
echo $num1+$num2; 
} 
sum("33","20");
```

Nullable type hints
```php
function myName(?string $text): void { 
if ($text) { 
echo "Text is: $text "; 
} 
else { 
echo "No text provided."; 
} }
myName("Jack"); 
myName(null);
```
#### Anonymous Functions (or Closures)
These are functions without a name. They can be stored in variables or passed as arguments to other functions.
* Creation & Execution Directly
```php
(function () 
 { 
 echo "Hello from the anonymous function!"; 
 })
 ();
```

* Assign to a Variable and Execute
```php
$greet = function($name) 
{ 
echo "Hello, " . $name . "!"; 
}; 
$greet("OSTAD");
```
* Arrow functions provide a more concise syntax for writing anonymous functions. are designed for simple, single-expression use-cases.
```php
$sum = fn($num1,$num2) =>$num1 * $num2; echo $sum(5,5);
```