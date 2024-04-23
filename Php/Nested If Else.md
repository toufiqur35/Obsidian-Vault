The nested if statement contains the if block inside another if block. The inner if statement executes only when specified condition in outer if statement is **true**.
```php
$a = 13;

if ($a > 10) {
  echo "Above 10";
  if ($a > 20) {
    echo " and also above 20";
  } else {
    echo " but not above 20";
  }
}
```