For loop is **a control structure that repeats a block of code as long as a condition is met**. It's usually used to repeat a block of code a certain number of times. The PHP for loop function can be used to iterate over a set of code for a set number of times.
### Example Explained
* The first expression, `$x = 0;`, is evaluated once and sets a counter to 0.
* The second expression, `$x <= 10;`, is evaluated _before_ each iteration, and the code block is only executed if this expression evaluates to true. In this example the expression is true as long as `$x` is less than, or equal to, 10.
* The third expression, `$x++;`, is evaluated _after_ each iteration, and in this example, the expression increases the value of `$x` by one at each iteration.
```php
for ($i = 1; $i <= 10; $i++) {
	echo"\n";
    echo $i;
}
/* example 2 */
for ($i = 1; ; $i++) {
	if ($i > 10) {
		break;
	}
	echo"\n";
	echo $i;
}
/* example 3 */
$i = 1;
for (; ; ) {
	if ($i > 10) {
		break;
	}
	echo"\n";
	echo $i;
	$i++;
}
/* example 4 */
for (
	$i = 1, 
	$j = 0; 
	$i <= 10; 
	$j += $i, 
	echo"\n";
	print $i, $i++
);
```

#### Revers for loop
```php
for ($i = 10; $i > 0; $i--) {
	echo"\n";
    echo $i;
}
```
#### Multiple stepping in for loop
```php
for($i = 10, $j = 0; $i > 0; $i-=1, $j++)
{
echo $i." ".$j;
echo "\n";
}

for($i = 0, $j = 0; $i<100; $i+=7,$j+=11)
{
	echo $i."\n";
	echo $j<100 ? $j."\n":'';
}
```


1. CPU->   AMD Ryzen 5 5600G
2. CPU Cooler->   Xtreme XJOGOS XJC400 180W CPU Air Cooler
3. Motherboard->   Asrock B450 Steel Legend AMD
4. RAM->   CORSAIR VENGEANCE RGB RS 8GB DDR4 3200MHz RAM
5. SSD->   Lexar NM620 256GB M.2 NVMe 
6. Storage->   Toshiba  1TB
7. Graphics Card->   GIGABYTE GeForce GT 710 2GB
8. Power Supply->   Thermaltake Smart BX1 550W
9. Casing
10. Monitor->   BenQ
11. Casing Cooler
12. Keyboard
13. Mouse
14. Headphone



