* The `__invoke()` magic method is a special method which is called when you try to call an object as if it were a function. Firstly, let’s see how it works, and then we’ll see the purpose of this magic method.

```php
class Student {
    private $name;
    private $email;
    public function __construct($name,$email)
    {
        $this->name = $name;
        $this->email = $email;
    }
    public function __invoke()
    {
        echo $this->name ." ".$this->email;
    }
}

$objStudent = new Student('John', 'john@tutsplus.com');
$objStudent();
```

* As you can see, the `$objStudent` object is treated as if it were a function, and as we’ve defined the `__invoke()` method, it’ll be called instead of giving you an error. The main purpose of the `__invoke()` method is that if you want to treat your objects as callable, you can implement this method.