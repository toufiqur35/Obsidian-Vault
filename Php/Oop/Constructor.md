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
* Pass parameters to the constructor just like you would with any other function or method.
* Constructor can assign value to class properties

```php
class Car { 
public $num1; 
public $num2; 

public function __construct($num1,$num2)
{ 
$this->num1 = $num1; 
$this->num2 = $num2; 
} 

function AddTwoNum()
{ 
//Inheritance Overriding Methods 
echo $this->num1+$this->num2; 
} 
} 
$myCar = new Car(2,3); 
$myCar->AddTwoNum();

//example 2
class Car { 
public $num1; 
public $num2; 

public function __construct($num1,$num2) 
{ 
$this->num1 = $num1; 
$this->num2 = $num2; 
}

function AddTwoNum($a,$b)
{ 
echo $a+$b; 
} 
} 
$myCar = new Car(2,3); 
$myCar->AddTwoNum(6,8);

//output:
//example: 5
//example2: 14
```