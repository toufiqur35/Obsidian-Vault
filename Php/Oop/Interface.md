* A PHP interface defines a contract which a class must fulfill. If a PHP class is a blueprint for objects, an interface is a blueprint for classes.
* all method public.

**Creating an Interface**
Following is an example of how to define an interface using the _interface_ keyword.

```php
  interface MyInterfaceName {
    public  function methodA();
    public  function methodB();
 }
  class MyClassName implements MyInterfaceName{
    public  function methodA() {  
      // method A implementation
    }  
    public  function methodB(){  
      // method B implementation
    }  
 }


//example
interface MyInterfaceName{ 

	public function method1(); 
	public function method2(); 

} 

class MyClassName implements MyInterfaceName{ 

	public function method1(){ 
		echo "Method1 Called" . "\n"; 
	} 

	public function method2(){ 
		echo "Method2 Called". "\n"; 
	} 
} 

$obj = new MyClassName; 
$obj->method1(); 
$obj->method2(); 

```