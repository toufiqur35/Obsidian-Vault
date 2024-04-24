#### Problem Name : Find Discount
## Problem Statement
Write a program to create a function that takes two arguments: the original price and the discount percentage as integers and returns the final price after the discount.
#### Input
The input consists of two integers: the original price and the discount.
#### Output
The output will print the final price after discount which will be a float number.
#### Constraints
N stands for any integer number.
- 0 ≤ |N| ≤ 100000
#### Example:
Enter numbers
#### Input:

```
50 20
```
#### Output:

```
Price: 40.00
```

#### Answer
```php
fscanf(STDIN,"%d %d",$originalPrice,$discount);
$discountPrice = ($originalPrice*$discount)/100;
$result = $originalPrice-$discountPrice;
print "Price: ".number_format((float)$result, 2, '.', '');

//output:
//Price: 40.00
```
