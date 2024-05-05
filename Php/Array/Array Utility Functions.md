* `array_unique()` Removes duplicate values from an array.
```php
$input = ["a", "b", "a", "c", "d", "b"]; 
$result = array_unique($input);
print_r($result);
```

* `array_reverse()` Returns an array with elements in reverse order. 
```php
$input = [1, 2, 3, 4, 5]; 
$result = array_reverse($input); 
print_r($result);
```

* `array_rand()` Picks one or more random entries out of an array.
```php
$input = ["apple", "banana", "cherry", "date", "fig"]; 
$randomKey = array_rand($input); 
echo $input[$randomKey]; 
$randomKeys = array_rand($input, 2);
print_r($randomKeys);
```

* `shuffle()` Shuffles (randomizes the order of) the elements in an array. 
```php

```

* `range()` Creates an array containing a range of elements. 
```php

```