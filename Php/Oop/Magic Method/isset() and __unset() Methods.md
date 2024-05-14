The `__isset()` magic method is called when you call the `isset()` method on inaccessible or non-existent object properties. Let’s see how it works through an example.

```php
class Student {
private $data = array();

public function __isset($name)
{
return isset($this->data[$name]);
}
}

$objStudent = new Student();
echo isset($objStudent->phone);
```

In the above example, the phone property is not defined in the class, and thus it’ll call the `__isset()` method.

On the other hand, the `__unset()` is a method called when you call the `unset()` method on inaccessible or non-existent object properties.