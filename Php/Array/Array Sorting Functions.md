
`sort()` - Sorts an array in ascending order. 
```php
$numbers = array(3, 1, 4, 1, 5); 
sort($numbers);
print_r($numbers);
```

`rsort()` - Sorts an array in descending order. 
```php
$numbers = array(3, 1, 4, 1, 5);
rsort($numbers);
print_r($numbers);
```

`asort()` - Sorts an array and maintains index association. 
```php
$fruit = array("key1" => "lemon", "key2" => "orange", "key3" => "banana"); asort($fruit);
print_r($fruit);
```

`arsort()` - Sorts an array in reverse order and maintains index association. 
```php
$fruit = array("key1" => "lemon", "key2" => "orange", "key3" => "banana"); arsort($fruit); 
print_r($fruit);
```

`ksort()` - Sorts an array by key. 
```php
$fruit = array("d" => "lemon", "a" => "orange", "b" => "banana"); 
ksort($fruit); 
print_r($fruit);
```

`krsort()` - Sorts an array by key in reverse order. 
```php
$fruit = array("d" => "lemon", "a" => "orange", "b" => "banana"); 
krsort($fruit); 
print_r($fruit);
```

`natsort()` - Sorts an array using natural order algorithm. 
```php
$files = array("img1.png", "img10.png", "img12.png", "img2.png"); 
natsort($files); 
print_r($files);
```

`natcasesort()` - Sorts an array using a case-insensitive natural order algorithm. 
```php
$files = array("Img1.png", "img10.png", "img12.png", "IMG2.png"); natcasesort($files); 
print_r($files);
```
`uasort()` - Sorts an array with a user-defined comparison function and maintains index 
association. 
```php
$people = array( "Peter" => 35, "Jack" => 32, "Mary" => 28); 
function ageComparator($a, $b) 
{ 
return $a - $b; 
} 
uasort($people , 'ageComparator'); 
print_r($people);
```

`uksort()` - Sorts an array by keys using a user-defined comparison function.
```php
$people = array( "Peter" => 35, "Jack" => 32, "Mary" => 28); 
function ageComparator($a, $b) 
{ 
return $a <=> $b; 
} 
uksort($people , 'ageComparator'); 
print_r($people);
```