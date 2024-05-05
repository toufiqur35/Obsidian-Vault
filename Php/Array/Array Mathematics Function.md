* `array_diff()` Computes the difference of arrays. It compares the values of the first array with the values of following arrays and returns the differences. 
```php
$array1 = ["a", "b", "c", "d"]; 
$array2 = ["b", "c"]; 
$result = array_diff($array1, $array2); 
print_r($result);
```

* `array_diff_assoc()` Computes the difference of arrays with additional index check.
```php
$array1 = ["a" => "green", "b" => "brown", "c" => "blue", "red"]; 
$array2 = ["a" => "green"]; 
$result = array_diff_assoc($array1, $array2); 
print_r($result);
```

* `array_diff_key()` Computes the difference of arrays using keys for comparison. 
```php
$array1 = ["blue" => 1, "red" => 2, "green" => 3]; 
$array2 = ["green" => 4, "yellow" => 7]; 
$result = array_diff_key($array1, $array2); 
print_r($result);
```

* `array_intersect()` Computes the intersection of arrays. /
```php
$array1 = ["a", "b", "c", "d"]; 
$array2 = ["b", "c", "e"]; 
$result = array_intersect($array1, $array2); 
print_r($result);
```

* `array_intersect_assoc()` Computes the intersection of arrays with additional index check. 
```php

```

* `array_intersect_key()` Computes the intersection of arrays using keys for comparison.
```php

``