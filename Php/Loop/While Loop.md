The **while** loop is the simple loop that executes nested statements repeatedly while the expression value is true. The expression is checked every time at the beginning of the loop, and if the expression evaluates to true then the loop is executed otherwise loop is terminated.
```php
// example 1
$i = 0;
while($i<10)
{
	$i++;
	echo "\n";
	echo $i;
}
// example 2
$i = 0;
while($i++<5)
{
	echo "\n";
	echo $i;
}
// example 3
$i = 0;
while(++$i<5)
{
	echo "\n";
	echo $i;
}
//output:
// example 1: 12345678910
// example 2: 12345
// example 3: 1234
```