* Method that gets executed whenever an object is instantiated from a class 
* The constructor method has a magic name: `__construct`

```php
class Car { 
public function __construct() 
{ 
$num1=10;
$num2=20; 
echo $num1+$num2; 
} 
} 
$myCar = new Car();

// output: 30
```

#### Constructor Parameters
