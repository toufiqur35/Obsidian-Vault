The break keyword is **used to break out of for loops, for-each loops, while loops, do..** **while loops and switch conditions**. In the switch block, all of the code following a case statement will be executed until a break keyword is found.
```php
for ($x = 0; $x < 10; $x++) {
  echo $x
  echo "\n";
  if ($x == 4) {
    break;
  }
}

//example 2
for ($x = 20; $x < 50; $x++) {
  if ($x % 4 == 0) {
    echo $x
	echo "\n";
    break;
  }
}

```

#### Continue
The PHP continue statement is used to continue the loop. It continues the current flow of the program and skips the remaining code at the specified condition.

The continue statement is used within looping and switch control structure when you immediately jump to the next iteration.

The continue statement can be used with all types of loops such as - for, while, do-while, and foreach loop. The continue statement allows the user to skip the execution of the code for the specified condition.
```php
```php
$x = 0;

while($x < 10) {
  if ($x == 4) {
    continue;
  }
  echo "The number is: $x <br>";
  $x++;
}
```
//outer loop  
for ($i =1; $i<=5; $i++) {  
//inner loop  
	for ($j=1; $j<=5; $j++) {  
	if (!($i == $j) ) {  
		continue;       //skip when i and j does not have same values  
		}  
		echo $i.$j;  
		echo "</br>";  
	}  
}
```