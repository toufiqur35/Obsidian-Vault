`array()` - Creates an array. 
```php
$fruits = array("apple", "banana", "cherry");
$fruits1 = ["apple", "banana", "cherry"];
echo $fruits[2];
```

`array_values()` - Returns all the values from the array. 
```php
$assoc = array("a" => "apple", "b" => "banana", "c" => "cherry");
$values = array_values($assoc);
echo $values[1];
```

`array_keys()` - Returns all the keys from the array. 
```php
$assoc = array("a" => "apple", "b" => "banana", "c" => "cherry"); 
$keys = array_keys($assoc);
echo $keys[1];
```

`array_combine()` - Combines two arrays: one for keys and the other for values.
```php
$keys = array("a", "b", "c"); 
$values = array("apple", "banana", "cherry"); 
$combined = array_combine($keys, $values);
```

`array_fill()` - Fills an array with values. 
```php

```

`array_push()` - Adds one or more elements to the end of an array.
```php

```

`array_pop( )` - Removes the last element from an array. 
```php

```

`array_unshift(`) - Adds one or more elements to the beginning of an array.
```php

```

`array_shift()` - Removes the first element from an array. 
```php

```

`array_splice()` - Removes a portion of the array and replaces it with something
```php

```

`array_slice()` - Extracts a portion of the array
```php

```