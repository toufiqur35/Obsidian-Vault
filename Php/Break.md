The break keyword is **used to break out of for loops, foreach loops, while loops, do..** **while loops and switch conditions**. In the switch block, all of the code following a case statement will be executed until a break keyword is found.
```php
for ($x = 0; $x < 10; $x++) {
  if ($x == 4) {
	echo $x
	echo "\n";
    break;
  }
}

//example 2
for ($x = 20; $x < 50; $x++) {
  if ($x % 4) {
    echo $x
	echo "\n";
    break;
  }
}
```