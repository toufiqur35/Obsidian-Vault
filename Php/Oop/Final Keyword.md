* If you declare a class as final, it means it cannot be extended (inherited).
* If you declare a method as final, it means it cannot be overridden by a subclass.

```php
final class Father { 
final public function print100() { 
for($i=0;$i<=100;$i++){ 
echo "$i"; 
} 
}
} 

class Son extends Father {
public function print100() { 
for($i=0;$i<=80;$i++){ echo "$i"; 
}
} 
}
```