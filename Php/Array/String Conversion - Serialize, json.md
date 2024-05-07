#### Array to String
* To convert an array to a string in PHP you can use implode($separator, $array)
* **The PHP implode() function accepts the input as an array and further converts it to a string**. This function uses the glue parameter, which also acts as the separator for the given array argument. Therefore this function accepts the array, converts its values into a string, and concatenates them using a separator.

```php
$array = array('PHP','array', 'to', 'string', 'conversion', 'example');  
echo implode(' ', $array);

//output: PHP array to string conversion example
```

#### Array to Serialize
* The serialize() function takes an array and converts it to a string.

```php
$array = array('apple', 'orange');
$string = serialize($array);
echo $string;
#output: a:2:{i:0;s:5:"apple";i:1;s:6:"orange";}
```

#### Array to `json`
* The `json_encode`() function converts an array to a JSON string. It takes an array as input and returns a JSON array representation.

```php
$array = array(
    'Name' => 'Leo',
    'Age' => 25,
);

$json = json_encode($array); 
echo $json;
//output: {"Name":"Leo","Age":25}
```

#### `json` to Array 
* The `json_decode`() function returns an object by default. The `json_decode`() function has a second parameter, and **when set to true, JSON objects are decoded into associative arrays**.

```php
$array = array(
    'Name' => 'Leo',
    'Age' => 25,
);

$json = json_encode($array);
$jsonDcode = json_decode($json);
print_r($jsonDcode) ;

//output: ( [Name] => Leo [Age] => 25 )
```