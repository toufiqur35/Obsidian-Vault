We can nest a ternary operator as **an expression inside another ternary operator**. We can use this to replace if…else if…else statements and switch statements.
```php
$f = 0;

($f == 0) ?
print("f is 0")
: ($f == 1)?
print("f is 1")
: 'anything';
```