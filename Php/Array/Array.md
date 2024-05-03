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

#### Associative arrays
* Associative arrays in PHP are arrays that use named keys instead of numeric indexes. 
* This - makes them more expressive and useful when dealing with key-value pairs. 
* Associative arrays can be defined using the array() function or the short array syntax [].
##### How to create
```php
$person1 = array(
"first_name" => "John", 
"last_name" => "Doe"
);
$person2 = [
"first_name" => "Jane", 
"last_name" => "Smith"
]; 
// Accessing Values
echo $person1["first_name"]; 
//Looping Through an Associative Array 
foreach ($person1 as $key => $value) 
{ 
echo "$key : $value "; 
}
```