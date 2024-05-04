
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

```

`array_merge()` - Merges one or more arrays. 
```php

```

`array_replace()` - Replaces values from one array to another. 
```php

```

`array_flip()` - Exchanges all keys with their associated values in an array. 
```php

```
`array_change_key_case()` - Changes the case of all keys in an array. 
```php

```

`array_column()` - Returns the values from a single column of the input array. 
```php

```