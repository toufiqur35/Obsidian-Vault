## Problem Statement
Write a program where you will be given an array arr[] of size N and an integer P. Find the triplet in the array which sums up to the given integer P.
### Input
The program will take an integer 𝑁N as the size of an array. Then it will take the integer values of the array 𝑎𝑟𝑟[]arr[]. Finally, it will take the target value 𝑃P.
### Output
The output will print the triplet numbers which will generate the sum.
### Constraints

- 0 ≤ N ≤ 100000
- 0 ≤ arr[] ≤ 100000
- 0 ≤ P ≤ 100000
### Example:
Enter numbers
#### Input:
```
6
12 3 4 1 6 9
24
```
#### Output:

```
3 9 12
```

#### Solution:

```php
 $line1 = fgets(STDIN);
 $n = trim(fgets(STDIN));
 $arr = explode(" ", $n);
 $P = fgets(STDIN);

function find_triplet($arr, $P) {
    $N = count((array)$arr);

    for ($i = 0; $i < $N - 1; $i++) {
        $hashMap = array();
        for ($j = $i + 1; $j < $N; $j++) {
            $current_sum = $arr[$i] + $arr[$j];
            $needed_sum = $P - $current_sum;
            if (isset($hashMap[$needed_sum])) {
                return array($arr[$i], $arr[$j], $needed_sum);
            }
            $hashMap[$arr[$j]] = true;
        }
    }
    return null;
}

$result = find_triplet($arr, $P);
sort($result);
echo implode(" ", $result);
```