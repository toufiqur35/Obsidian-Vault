The `__toString()` magic method allows you to define what you would like to display when an object of the class is treated like a string. If you use `echo` or `print` on your object, and you haven’t defined the `__toString()` method, it’ll give an error.

```php
class Student {
    private $name;
    private $email;
    public function __construct($name, $email)
    {
        $this->name = $name;
        $this->email = $email;
    }
    public function __toString()
    {
        return 'Student name: '.$this->name
        . '<br>'
        . 'Student email: '.$this->email;
    }
}

$objStudent = new Student('John', 'john@tutsplus.com');

echo $objStudent;
```

In the above example, when you echo the `$objStudent` object, it’ll call the `__toString()` method. In that method, you can decide what you would like to display. If you hadn’t defined the `__toString()` method, this would have resulted in an error!