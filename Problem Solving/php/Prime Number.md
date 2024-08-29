#### PHP Program to Print Prime Number from 1 to N
#### Algorithm to print prime numbers:  
- First, take the number N as input.
- Then use a for loop to iterate the numbers from 1 to N
- Then check for each number to be a prime number. If it is a prime number, print it.

```php
function isPrime($n) {
    if ($n == 1 || $n == 0) {
        return false;
    }
    // Run a loop from 2 to sqrt(n)
    for ($i = 2; $i <= sqrt($n); $i++) {
        if ($n % $i == 0) {
            return false;
        }
    }
    return true;
}
	// Driver code
	$N = 50;
	// Check for every number from 1 to N
	for ($i = 1; $i <= $N; $i++) {
	    if (isPrime($i)) {
	        echo $i . " ";
	 }
}
```