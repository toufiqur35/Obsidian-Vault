The [Fibonacci series](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/) is a series of elements where, the previous two elements are added to get the next element, starting with 0 and 1. In this article, we will learn about how to generate a Fibonacci series in PHP using iterative and recursive way. Given a number n, we need to find the Fibonacci series up to the nth term.
```php
$veryold = 0;
$old = 1;
$new = 1;
for($i=0;$i<10;$i++)
{
	$old = $new;
	$new = $old + $veryold;
	$veryold = $old;
	echo $veryold." ";
}

// output;
// 1 1 2 3 5 8 13 21 34 55
```