## Problem Statement 1
Write a program to verify that all the brackets in a given string are correctly matched and nested.
### Input
The program will take a string 𝑆S as input.
### Output
The output will either print "Brackets are balanced." if the brackets are matched or print "Brackets are not balanced."
### Constraints

- 0 ≤ |S| ≤ 100000

### Example:

Enter string
#### Input:

```
[{{()}}]
```
#### Output:

```
Brackets are balanced.
```

### Solving
```php
 $input = trim(fgets(STDIN));
     if(isValidStack($input)){
        print "Brackets are balanced.";
    }
    else{
        print "Brackets are not balanced.";
    }
    function isValidStack($input) {
        $st = new SplStack();
        for($i=0;$i<strlen($input);$i++)
        {
            $item = $input[$i];
            //print $item." ".isOpening($item)."\n";
            if(isOpening($item))
            {
                $st->push($item);
            }
            else{
                if($st->isEmpty()) return false;
                if(!isMatched($st->top(),$item)) return false;
                $st->pop();
            }
        }
        if($st->isEmpty()) return true;
        return false;
    }


   function isMatched($opening, $closing){
        if($opening == "(" && $closing == ")") return true;
        if($opening == "{" && $closing == "}") return true;
        if($opening == "[" && $closing == "]") return true;
        return false;

    }

    function isOpening($bracket) {
        if($bracket == "(" || $bracket == "{" || $bracket == "[") return true;
        return false;
    }
```

## Problem Statement 2

Write a program to evaluate Postfix expression.A postfix expression is an expression where the operator appears after the operands.
### Input

The program will take a string 𝑆S as input.
### Output

The output will print the result after evaluation which will be an integer.
### Constraints

- 0 ≤ |S| ≤ 10000
- Only characters from 0-9 will be used
- - - - / will be there as opertor along with ( ) in input
### Example:

Enter string
#### Input:

```
56*
```
#### Output:

```
30
```
## Solution

```php
$input = trim(fgets(STDIN));
    $st = new SplStack();
    for($i=0;$i<strlen($input);$i++)
        {
           $item = $input[$i];
           if(isNumber($item)){
            $st->push($item);
           }else{
            $first = $st->pop();
            $second = $st->pop();
            $res = calculate($second,$first,$item);
            $st->push($res);
           }
        }
    print (int)$st->top();
    function calculate($first,$second,$operator){
        switch($operator){
            case '+':
           return $first+$second;
            break;
            case '-':
            return $first-$second;
            break;
            case '*':
            return $first*$second;
            break;
            case '/':
            return $first/$second;
            break;
        }
    }
    
    function isNumber($item){
        return $item >= "0" && $item<="9";
    }

```

## Problem Statement 3

Write a program to evaluate Prefix expression.A prefix expression is an expression where the operator appears before the operands.
### Input
The program will take a string 𝑆S as input.
### Output
The output will print the result after evaluation which will be an integer.
### Constraints
- 0 ≤ |S| ≤ 10000
- Only characters from 0-9 will be used
- - - - / will be there as opertor along with ( ) in input
### Example:
Enter string
### Input:

```
*56
```
#### Output:

```
30
```

## Solution

```php
 $input = trim(fgets(STDIN));
    $st = new SplStack();
    for($i= strlen($input) - 1 ; $i>=0 ; $i--)
        {
           $item = $input[$i];
           if(isNumber($item)){
            $st->push($item);
           }else{
            $first = $st->pop();
            $second = $st->pop();
            $res = calculate($first,$second,$item);
            $st->push($res);
           }
        }
        
    print (int)$st->top();
    
    function calculate($first,$second,$operator){
        switch($operator){
            case '+':
            return $first+$second;
            break;
            case '-':
            return $first-$second;
            break;
            case '*':
            return $first*$second;
            break;
            case '/':
            return $first/$second;
            break;
       }
    }

	function isNumber($item){
        return $item >= "0" && $item<="9";
    }
```