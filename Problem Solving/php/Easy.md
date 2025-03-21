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

## 3 Problem Statement - Positivity

Write a program to check if an array contains more positivity than negativity.An array has more positivity if it contains strictly more unique positive values than unique negative values. If the number of positive and negative values are equal then it is also taken as negativity.
### Input

The program will take an integer 𝑁N as the size of an array. Then it will take the integer values of the array 𝑀[]M[].
### Output

The output will print either "Positivity" or "Negativity"
### Constraints

- 0 ≤ |N| ≤ 10000
- -10000 ≤ |M[]| ≤ 10000
### Example:

Enter numbers
#### Input:

```
5
1 -3 6 -2 -8
```
#### Output:

```
Negativity
```
### Solution

```php
$line1 = trim(fgets(STDIN));
$line2 = trim(fgets(STDIN));

$n = (int)$line1;
$data = explode(" ", $line2);

$pos = 0;
$neg = 0;
for($i=0;$i<$n; $i++)
    {
        if($data[$i]>0){
            $pos++;
        }else{
            $neg++;
        }
    }
print $pos>$neg?"Positivity":"Negativity";
```



### 4. Sum Digits: Odd or Even
### Problem Statement

Write a program which will determine whether the sum of all the digits of the number is even or odd.
### Input

The program will take an integer 𝑁N as input.
### Output

The output will print either "Odd" or "Even"
### Constraints

- 0 ≤ |N| ≤ 100000
### Example:

Enter number
#### Input:

```
123
```
#### Output:

```
Even
```

#### Solution

```php
fscanf(STDIN,"%s",$n);
    $sum = 0;
    for($i=0;$i<strlen($n);$i++){
        $sum +=(int)$n[$i];
    }
    if($sum % 2 == 0){
         print "Even";
    }
    else{
         print "Odd";
    }
```



Computer Networking Lab
530222
Software Engineering Lab
530220
Embedded System Programming Lab
530224
Submission Date: 26/06/2024