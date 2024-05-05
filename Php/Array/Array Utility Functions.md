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
$randomKeys = array_rand($input, 2);
print_r($randomKeys);
```

* `shuffle()` Shuffles (randomizes the order of) the elements in an array. 
```php
$numbers = [1, 2, 3, 4, 5]; 
shuffle($numbers); 
print_r($numbers)
```

* `range()` Creates an array containing a range of elements. 
```php
// Create an array of numbers from 1 to 5 
$numbers = range(1, 5); 
print_r($numbers); 
// Create an array of letters from 'a' to 'e' 
$letters = range('a', 'e');
print_r($letters); 
// Using a step value 
$evenNumbers = range(0, 10, 2); 
print_r($evenNumbers);
```