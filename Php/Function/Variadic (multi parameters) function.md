* Functions that accept an indefinite number of arguments. 
* They use the `(...)` spread operator
```php
//example 1
function sum(int ...$numbers):int{
	$result = 0;
	for($i=0;$i<count($numbers);$i++)
		{
			$result += $numbers[$i];
		}
	return $result;
}
echo sum(3,4,5,6,7,8);
//example 2
function myFamily($lastname, ...$firstname) {
	$txt = "";
	$len = count($firstname);
	for($i = 0; $i < $len; $i++) {
		$txt = $txt."Hi, $firstname[$i] $lastname.\n";
	 }
	return $txt;
}
$a = myFamily("Doe", "Jane", "John", "Joey");
echo $a;

//output:
// example 1: 33
// example 1: Hi, Jane Doe. Hi, John Doe. Hi, Joey Doe.
```