* Abstract classes cannot be instantiated on their own but can be sub classed.
*  common code `rakta use kora hoi`
* বিমূর্ত ক্লাস এবং পদ্ধতিগুলি হল যখন প্যারেন্ট ক্লাসের একটি নামকরণ পদ্ধতি থাকে, তবে কাজগুলি পূরণ করতে এর চাইল্ড ক্লাস(গুলি) প্রয়োজন৷ একটি বিমূর্ত শ্রেণী হল **এমন একটি শ্রেণী যাতে অন্তত একটি বিমূর্ত পদ্ধতি থাকে** । একটি বিমূর্ত পদ্ধতি একটি পদ্ধতি যা ঘোষণা করা হয়, কিন্তু কোডে প্রয়োগ করা হয় না।

```php
// Parent class  
abstract class Car {  
  public $name;  
  public function __construct($name) {  
    $this->name = $name;  
  }  
  abstract public function intro() : string;  
}  
  
// Child classes  
class Audi extends Car {  
  public function intro() : string {  
    return "Choose German quality! I'm an $this->name!";  
  }  
}  
  
class Volvo extends Car {  
  public function intro() : string {  
    return "Proud to be Swedish! I'm a $this->name!";  
  }  
}  
  
class Citroen extends Car {  
  public function intro() : string {  
    return "French extravagance! I'm a $this->name!";  
  }  
}  
  
// Create objects from the child classes  
$audi = new audi("Audi");  
echo $audi->intro();  
echo "<br>";  
  
$volvo = new volvo("Volvo");  
echo $volvo->intro();  
echo "<br>";  
  
$citroen = new citroen("Citroen");  
echo $citroen->intro();
```

