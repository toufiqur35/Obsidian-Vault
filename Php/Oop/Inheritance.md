* Inheritance sets up a "like parent, like child" relationship between classes. 
* Instead of rewriting code, the child class can reuse or change what it gets from the parent. 
* One class (the child) can use everything from another class (the parent).

```php
class Father { 
public function print100() 
{ 
	for($i=0;$i<=100;$i++)
	{ 
		echo "$i"; 
	} 
} 
} 
class Son extends Father 
{ 
} 
$SonObject = new Son(); 
$SonObject->print100();
```