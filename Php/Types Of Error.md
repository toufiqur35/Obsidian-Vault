Parse Error (Syntax Error): 
1. Caused by a mistake in the PHP syntax. 
2. Common examples include missing semicolons or curly braces. 
3. Execution stops immediately when a parse error occurs.

```php
if ($_SERVER["REQUEST_METHOD"] == "POST") 
{
echo "Hello, World" 
}
```

Fatal Error: 
1. Caused when PHP understands what you've written, but what you're asking it to do can't be done. 
2. Common examples include calling an undefined function or class. 
3. Execution stops immediately when a fatal error occurs.

```php
if ($_SERVER["REQUEST_METHOD"] == "GET") 
{ 
echo myUndefinedFunction(); 
}
```

Warning Error: 
1. Less severe than fatal errors. 
2. They indicate something that's probably an error, but not so severe that execution must be halted. 
3. An example might be including a file that doesn't exist using the include() function. The script will continue to execute after the warning.

```php
if ($_SERVER["REQUEST_METHOD"] == "GET") 
{ 
include("non_existent_file.php"); 
echo "Hello"; 
}
```

Notice Error: 
1. Less severe than warnings. 
2. Indicate something that might be an error or might be perfectly fine, but it's worth investigating. 
3. A common example is trying to access an undefined variable.

```php
if ($_SERVER["REQUEST_METHOD"] == "GET") 
{ 
$x = "Hello, World!"; 
echo $y; 
}
```

Deprecated Error:  

```php

```
