#### Indexed Arrays 
* PHP array is an ordered map (contains value on the basis of key). It is used to hold multiple values of similar type in a single variable.
* You can create an indexed array using the array() function or the short array syntax.
##### How to create
```php
$array1 = array("apple", "banana", "cherry"); 
$array2 = ["apple", "banana", "cherry"]; 
//Accessing Values 
echo $array1[0]; 
echo $array2[0]; 
//For Loop Through an Indexed Array 
for ($i = 0; $i < count($array1); $i++) 
{ 
echo $array1[$i] . "  "; 
} 
//ForEach Loop Through an Indexed Array 
foreach ($array1 as $value) 
{ 
echo $value . "  "; 
}
```