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

```

#### Array to `json`
* The `json_encode`() function converts an array to a JSON string. It takes an array as input and returns a JSON array representation.

```php

```