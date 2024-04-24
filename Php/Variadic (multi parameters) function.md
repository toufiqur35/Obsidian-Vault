* Functions that accept an indefinite number of arguments. 
* They use the `(...)` spread operator
```php
function sum(...$numbers) 
{ 
echo array_sum($numbers); 
} 
sum(1,2,3,4,5); 
function sum(...$numbers) { 
echo $numbers[0]; 
} 
sum(1,2,"3",4,5);
```