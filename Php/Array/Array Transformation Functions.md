
`array_map()` - Applies a callback function to the elements of one or more arrays.
```php
function square($n) { 
return $n * $n; 
} 
$numbers = array(1, 2, 3, 4); 
$squaredNumbers = array_map('square', $numbers); 
print_r($squaredNumbers);
```

`array_filter()` - Filters elements of an array using a callback function. 
```php
function is_even($n) {
return $n % 2 == 0; 
} 
$numbers = array(1, 2, 3, 4); 
$evenNumbers = array_filter($numbers, 'is_even'); 
print_r($evenNumbers);
```

`array_merge()` - Merges one or more arrays. 
```php
$arr1 = array("apple", "banana"); 
$arr2 = array("cherry", "date"); 
$merged = array_merge($arr1, $arr2);
print_r($merged);
```

`array_replace()` - Replaces values from one array to another. 
```php
$base = array("apple", "banana", "cherry"); 
$replacements = array(0 => "apricot", 2 => "date"); 
$replaced = array_replace($base, $replacements); 
print_r($replaced);
```

`array_flip()` - Exchanges all keys with their associated values in an array. (swap value and key)
```php
$input = array("a" => 1, "b" => 2, "c" => 3); 
$flipped = array_flip($input); 
print_r($flipped);
//output
//Array([1] => a,[2] => b,[3] => c)
```
`array_change_key_case()` - Changes the case of all keys in an array. 
```php
$input = array("First" => 1, "SecONd" => 4); 
$result = array_change_key_case($input, CASE_UPPER); 
print_r($result);
```

`array_column()` - Returns the values from a single column of the input array. 
```php
$records = array( 
array('id' => 2135, 'first_name' => 'John', 'last_name' => 'Doe'), 
array('id' => 3245, 'first_name' => 'Sally', 'last_name' => 'Smith'), 
array('id' => 5342, 'first_name' => 'Jane', 'last_name' => 'Jones') 
);
$firstNames = array_column($records, 'first_name'); 
print_r($firstNames);
```