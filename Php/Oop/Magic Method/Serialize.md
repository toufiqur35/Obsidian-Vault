#### Array to Serialize
* The serialize() function takes an array and converts it to a string.

```php
$array = array('apple', 'orange');
$string = serialize($array);
echo $string;
#output: a:2:{i:0;s:5:"apple";i:1;s:6:"orange";}
```

#### Serialize to Array 
* The `unserialize`() function converts serialized data back into actual data/array.

```php
$array = array('apple', 'orange');
$string = serialize($array);
$Array2 = unserialize($string);
print_r($Array2);
#output: Array
		// (
		// [0] => apple
		// [1] => orange
		// )
