* The __get() method is a magic method in PHP that is automatically called when an attempt is made to access an inaccessible (private or protected) or non-existing property of an object.

```php
class Student {

    private $data = array();

    public function __set($name, $value)

    {

        $this->data[$name] = $value;

    }

    public function __get($name)

    {

        if(isset($this->data[$name])) {

            return $this->data[$name];

        }

    }

}

$objStudent = new Student();

// __set() called

$objStudent->phone = '0491 570 156';  

// __get() called

// Output: 0491 570 156

echo $objStudent->phone;

//example 2
class abc{
private $data = ['name'=>'sobuj','age'=>24];
public function __get($key)
	{
		if(array_key_exists($key, $this->data))
		{
			return $this->data[$key];
		}
		else
		{
			return "This key $key is not define";
		}
	}
}

$test = new abc();
echo $test->name;
```