#### for-each loop
```php
//$cars = array("Volvo", "BMW", "Toyota");
$cars = ["Volvo", "BMW", "Toyota"];
foreach($cars as $car)
{
echo $car."\n";
}
```

Print both the key and the value from the `$members` array:

```php
$members = array("Peter"=>"35", "Ben"=>"37", "Joe"=>"43");

foreach ($members as $x => $y) {
  echo "$x : $y <br>";
}
```