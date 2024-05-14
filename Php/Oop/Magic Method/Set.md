* The `__set()` magic method is called when you try to set data to inaccessible or non-existent object properties. The purpose of this method is to set extra object data for which you haven’t defined object properties explicitly.

```php
class Student {
    private $data = array();
    public function __set($name, $value)
    {
	 $this->data[$name] = $value;
    }
}
$objStudent = new Student();
// __set() called
$objStudent->phone = '0491 570 156';
```

* As you can see in the above example, we’re trying to set the `phone` property, which is non-existent. And thus, the `__set()` method is called. The first argument of the `__set()` method is the name of the property which is being accessed, and the second argument is the value we’re trying to set.