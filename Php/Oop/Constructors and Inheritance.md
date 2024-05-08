* If a child class has its own constructor, the parent class's constructor will not be automatically called. 
* Use parent::__construct() if you want to explicitly call the base class's constructor

```php
class Father { 
public function __construct() {
echo "Father constructor"; 
} 
} 

class Son extends Father { 
public function __construct() { 
parent::__construct(); 
echo " and Son constructor"; 
} 
} 
$newObj = new Son();

//output: Father constructor and Son constructor
```