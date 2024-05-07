The `array_reduce`() function is a inbuilt function of PHP. The `array_reduce`( ) function is used to reduce the array to a single value using a callback function.

```php
$n=array(1,2,3,4,5);
function sum($oldValue,$newValue)  //oldValue,newValue
{  
return $oldValue + $newValue;  
}  
print_r(array_reduce($n,"sum"));

//output: 15

//example 2
function userfunction($x1,$x2)  
{  
return $x1 ." ". $x2;  
}  
$a=array("PHP","java","python");  
print_r(array_reduce($a,"userfunction"));

//output: PHP java python
```