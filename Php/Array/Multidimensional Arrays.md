* `array_multisort()` This function can be used to sort multiple arrays at once or a multi-dimensional array by one or more dimensions. 
```php
$names = ["Tina", "Bob", "Alice"]; 
$ages = [28, 22, 25]; 
array_multisort($names, $ages);
print_r($names); 
print_r($ages);
```

* `array_column()` This function returns the values from a single column in the input array. 
```php
$users = [ ['id' => 1, 'name' => 'Alice', 'email' => 'alice@example.com'], 
		   ['id' => 2, 'name' => 'Bob', 'email' => 'bob@example.com'], 
		   ['id' => 3, 'name' => 'Tina', 'email' => 'tina@example.com'], 
		]; 
$names = array_column($users, 'name'); 
print_r($names);
```

* `array_map()` This function applies a callback to the elements of the given arrays and returns an array containing all the elements after applying the callback function.
```php

```