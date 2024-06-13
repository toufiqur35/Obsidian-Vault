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