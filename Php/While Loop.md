The **while** loop is the simple loop that executes nested statements repeatedly while the expression value is true. The expression is checked every time at the beginning of the loop, and if the expression evaluates to true then the loop is executed otherwise loop is terminated.
```php
$i = 0;
while($i<10)
{
	$i++;
	echo "\n";
	echo $i;
}
```