* A destructor is called when the object is destructed or the script is stopped or exited.
* If you create a `__destruct()` function, PHP will automatically call this function at the end of the script.
* Notice that the destruct function starts with two underscores (__)!
* The example below has a __construct() function that is automatically called when you create an object from a class, and a __destruct() function that is automatically called at the end of the script
* আপনি যদি একটি `__destruct()` ফাংশন তৈরি করেন, তাহলে PHP স্বয়ংক্রিয়ভাবে স্ক্রিপ্টের শেষে এই ফাংশনটিকে কল করবে।

```php
class Fruit
{
public $name;
public $color;
function __construct($name, $color)
	{
		$this->name = $name;
		$this->color = $color;
	}

function hello()
	{
		echo "Hello Everyone \n";
	}

function __destruct()
	{
		echo "The fruit is {$this->name} and the color is {$this->color}.\n";
	}
}

$apple = new Fruit("Apple", "red");
$apple->hello();

//output:
// Hello Everyone
// The fruit is Apple and the color is red.
```