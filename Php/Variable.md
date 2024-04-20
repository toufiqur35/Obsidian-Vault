#### Variable Naming Conventions
* Variable names in PHP start with a dollar sign ($) 
* The name must begin with a letter or underscore ( _ ) , followed by letters, numbers, or underscores. 
* Variable names are case-sensitive, meaning $myVariable and $myvariable are treated as different variables. 
* PHP does not require you to declare a variable before using it ; it automatically creates the variable when you assign a value to it.
```php
$name="John"; 
$age=30;
```

#### Variable Types 
PHP is a loosely typed language, which means you don't need to declare the data type of a variable explicitly. PHP determines the data type based on the value assigned to it. Common data types in PHP include.
* **Strings:** Textual data enclosed in single **('')** or double **("")** quotes.
* **Integers:** Whole numbers. 
* **Floats (or Doubles):** Numbers with decimal points. Booleans: True or false values. 
* **Arrays:** Ordered collections of data. 
* **Objects:** Instances of user-defined classes. 
* **Null:** Represents a variable with no value.

```php
$name="John Smith"; 
$age=30; 
$price= 19.99; 
$isStudent=true;
$fruits=array(`"apple"`,` "banana"`,` "cherry"`);
class Person { 
	public $name; 
	public $age; 
} 
$person1 = new Person(); 
$person1->name = "Alice"; 
$person1->age = 25; 
$noValue = null;
```