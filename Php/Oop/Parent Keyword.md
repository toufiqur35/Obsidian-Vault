* You can call the parent class's method using the parent keyword.

```php
class Father { 
public function print100() { 
for($i=0;$i<=100;$i++){ 
echo "$i"; 
} 
} 
} 

class Son extends Father {
public function CallFromFather() {
parent::print100(); 
} 
} 
$SonObject = new Son(); 
$SonObject->CallFromFather();
```