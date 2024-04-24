#### 1. Problem Name : Find Discount
### Problem Statement
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

#### 2. Problem Name : Build Toy Cars
###`` Problem Statement

Suppose, you work in a toy car workshop, and your job is to build toy cars from a collection of parts. Each toy car needs 4 wheels, 1 car body, and 2 figures of people to be placed inside. Write a program which will calculate how many complete toy cars can be made, given the total number of wheels, car bodies and figures available.
#### Input
The input consists of three integers: number of wheels, car bodies, figures.
#### Output
The output will print the number of cars.
#### Constraints
N stands for any integer number.
- 0 ≤ |N| ≤ 100000
#### Example:
Enter numbers
#### Input:

```
43 15 87
```
#### Output:

```
10
```

#### Answer
```php
fscanf(STDIN,"%d %d %d",$wheels,$bodis,$figure);
$wheelsCar=floor($wheels/4);
$bodisCar=$bodis;
$figureCar=floor($figure/2);
print min($wheelsCar,$bodisCar,$figureCar);

//output
// 10
```