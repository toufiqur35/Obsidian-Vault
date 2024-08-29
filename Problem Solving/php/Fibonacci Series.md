## Problem Statement
Write a program to print fibonacci series.
### Input
The program will take an integer NN as input.
### Output
The output will print a series of fibonacci numbers.
### Constraints
- 0 ≤ N ≤ 1000
### Example:
Enter Number
#### Input:

```
7
```

#### Output:

```
0 1 1 2 3 5 8
```

#### Solutions:

```php
fscanf(STDIN,"%d",$n);

    if($n== 1){
        print "0";
    }else{
        $a = 0;
        $b = 1;
        print $a." ".$b." ";
        for($i=1;$i<$n-1;$i++)
        {
            $temp = $a+$b;
            $a = $b;
            $b = $temp;
            echo $temp." ";
        }
      }
```