## Problem Statement

Write a program to create a function which counts how many lone 0s appear in a given number. Lone means the number doesn't appear twice or more in a row. Previous and next numbers are not zeroes. For example - countLoneZeroes(10101) ➞ 2

### Example:
Enter number
#### Input:
```
10101
```
#### Output:

```
2
```

#### Solution:

```php
fscanf(STDIN, "%d", $n);

function countZeroes($n) {
    $str = strval($n);
    $length = strlen($str);
    $count = 0;

    for ($i = 0; $i < $length; $i++) {
        if ($str[$i] == '0') {
            $prev = ($i == 0) ? null : $str[$i - 1];
            $next = ($i == $length - 1) ? null : $str[$i + 1];
            if($str[0] == 0){
                $count = 0;
            }elseif ($prev !== '0' && $next !== '0') {
                $count++;
            }
        }
    }
    return $count;
}
echo countZeroes($n);
```
