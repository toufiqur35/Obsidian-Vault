**==All Subject:==**
1. 

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

#### Recursion and Recursive Functions `niga niga call korba`
Recursive functions are **a powerful tool in PHP that can simplify complex problems by breaking them down into smaller sub-problems**. However, they must be used with care and attention to detail to ensure that they terminate correctly and do not consume excessive resources.
```php
function factorial($n) 
{ 
if ($n == 0) { 
	return 1; 
} 
else { 
	return $n * factorial($n-1); 
} 
}
echo factorial(5);

//example 2
function printN($i)
{
if($i>10)
{
	return;
}
	echo $i."\n";
	$i++;
	printN($i);
}
printN(0);
//another
function printN($counter,$end)
{
if($counter>$end)
{
	return;
}
	echo $counter."\n";
	$counter++;
	printN($counter,$end);
}
printN(0,5);

//another
function printN($counter,$end,$steap=1)
{
if($counter>$end)
{
	return;
}
	echo $counter."\n";
	$counter+=$steap;
	printN($counter,$end,$steap);
}
printN(0,5,2);
```

#### Callback Function
Function that is passed as an argument to another function and is executed after the completion of that function. This pattern is quite common in programming, especially in scenarios like event handling, asynchronous operations, or functions that require custom logic.
```php
function sum($a, $b) 
{ 
echo $a + $b; 
} 
function calculate($num1, $num2, $callback) 
{
return $callback($num1, $num2); 
} 
calculate(5, 3, 'sum');
```

Basic Return Types
```php
function getAge(): int 
{ 
return 25; 
}
function isAdult(int $age): bool 
{ 
return $age >= 18; 
} 
echo getAge(); 
echo isAdult(11)
```

Nullable Return Type
```php
function findUsername(int $id): ?string
{ 
if ($id === 1) 
{ 
return "JohnDoe"; 
} 
return null; // It's valid because of the ? before string 
} 
echo findUsername(2);
```

Return Type of void
```php
function logMessage(string $message): void 
{ 
echo $message; 
} 
logMessage("Hello");
```

Union Return Types
```php
function sum($num1,$num2):int|string
{
return $num1+$num2; 
} 
echo sum("33","20");
```

#### Strict mode in PHP
Affects how type hints are enforced. 
By default, PHP will try to coerce values of the wrong type to match the expected type. 
In strict mode, PHP will throw a Type Error if the provided value does not exactly match the expected type.
```php
declare(strict_types=1); 
function add(int $a, int $b): int 
{ 
return $a + $b; 
} 
echo add("5", "10");
```

#### Variable Scope in PHP Function
ভেরিয়েবল স্কোপস: একটি ভেরিয়েবলের স্কোপ **প্রোগ্রামের মধ্যে তার ব্যাপ্তি হিসাবে সংজ্ঞায়িত করা হয় যার মধ্যে এটি অ্যাক্সেস করা যেতে পারে** , অর্থাৎ একটি ভেরিয়েবলের সুযোগ হল প্রোগ্রামের সেই অংশ যার মধ্যে এটি দৃশ্যমান বা অ্যাক্সেস করা যেতে পারে। স্কোপের উপর নির্ভর করে, PHP এর তিনটি পরিবর্তনশীল স্কোপ রয়েছে।
PHP has three different variable scopes:
- local
- global
- static
## Global and Local Scope

A variable declared **outside** a function has a GLOBAL SCOPE and can only be accessed outside a function:
```php
$x = 5; // global scope
function myTest() {
  echo $x; //eror
}
myTest();
echo $x; //run
```
## PHP The global Keyword
The `global` keyword is used to access a global variable from within a function.
To do this, use the `global` keyword before the variables (inside the function):
```php
$x = 5;
$y = 10;

function myTest() {
  global $x, $y;
  $y = $x + $y;
}

myTest();
echo $y; // outputs 15

//another
$name = "Sobuj";
function doSomthing()
{
	echo $GLOBALS['name'];
}
doSomthing();// outputs Sobuj
```
#### Static
এটি ভেরিয়েবল, পদ্ধতি, ব্লক এবং নেস্টেড ক্লাসের সাথে ব্যবহার করা যেতে পারে। এটি একটি কীওয়ার্ড যা **প্রদত্ত ক্লাসের একই পরিবর্তনশীল বা পদ্ধতি ভাগ করতে ব্যবহৃত হয়** । মূলত, স্ট্যাটিক একটি ধ্রুবক পরিবর্তনশীল বা একটি পদ্ধতির জন্য ব্যবহৃত হয় যা একটি ক্লাসের প্রতিটি উদাহরণের জন্য একই। একটি শ্রেণীর প্রধান পদ্ধতি সাধারণত স্ট্যাটিক লেবেল করা হয়.
```php
function doSomthing()
{
static $i;  //protibar ar man save kora rakba
$i = $i ?? 0; // ?? null kina check korba
$i++;
echo $i;
echo "\n";
}
doSomthing();
doSomthing();
doSomthing();
doSomthing();
```