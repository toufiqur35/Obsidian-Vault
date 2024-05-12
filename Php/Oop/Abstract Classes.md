* Abstract classes cannot be instantiated on their own but can be sub classed.
*  common code `rakta use kora hoi`

```php
abstract class Father { 
public function print100() { 
for($i=0;$i<=100;$i++){ 
echo "$i"; 
} 
}
} 
class Son extends Father { } 
$SonObject = new Son(); 
$SonObject->print100();
```