* Class allow developers to encapsulate related data and functions into a single entity. 
* Making it easier to manage and extend code An object is an instance of a class. 
* You create an object of a class using the new keyword.

```php
class Car { 
public $color = "red"; 
public function drive() { 
echo "Car is driving!"; 
} 
} 
$myCar = new Car(); 
echo $myCar->color."\n"; 
$myCar->drive();

//output: 
		//red
		//Car is driving!
```