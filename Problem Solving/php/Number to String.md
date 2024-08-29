## Problem Statement
Write a program to convert number into string. The program will print every digit of the number as a string.
### Input
The program will take an integer NN as input.
### Output
The output will print strings.
### Constraints
- 0 ≤ N ≤ 1000
### Example:
Enter Number
#### Input:

```
203
```

#### Output:

```
two zero three
```


#### Solutions:

```php
 fscanf(STDIN,"%s",$str);

    $digitToWord = [
    '0' => 'zero',
    '1' => 'one',
    '2' => 'two',
    '3' => 'three',
    '4' => 'four',
    '5' => 'five',
    '6' => 'six',
    '7' => 'seven',
    '8' => 'eight',
    '9' => 'nine'
];

for ($i = 0; $i < strlen($str); $i++) {
    print $digitToWord[$str[$i]]." ";
}
```