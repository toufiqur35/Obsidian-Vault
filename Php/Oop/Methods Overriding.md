* Subclasses can override inherited methods from the superclass.

```php
class Father { 
public function print100() { 
for($i=0;$i<=100;$i++){ 
echo "$i"; 
} 
} 
}

class Son extends Father { 
public function print100() { 
for($i=0;$i<=80;$i++){ 
echo "$i"; 
} 
} 
} 
$SonObject = new Son(); 
$SonObject->print100();
```