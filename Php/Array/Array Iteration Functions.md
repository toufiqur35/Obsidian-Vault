
`array_walk()` - Applies a user-defined function to each item in an array. 
```php
$fruits = array("apple", "banana", "cherry"); 
function test_alter(&$item, $key, $prefix) 
{ 
$item = "$prefix: $item"; 
} 
array_walk($fruits, 'test_alter', 'fruit'); 
print_r($fruits);
```

`array_walk_recursive()` - Applies a user-defined function recursively to each item in an array. 
```php
$sweet = array('a' => 'apple', 'b' => array('p' => 'pear', 'c' => 'cherry')); function test_print($item, $key) 
{ 
echo "$key holds $item\n"; 
} 
array_walk_recursive($sweet, 'test_print');
```

`array_reduce()` - Iteratively reduces the array to a single value using a callback function. 
```php
$numbers = array(1, 2, 3, 4, 5); 
function sum($carry, $item) 
{ 
$carry += $item; 
return $carry; 
} 
$result = array_reduce($numbers, 'sum'); 
echo $result; 
// Outputs: 15
```