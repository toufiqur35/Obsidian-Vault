PHP, constants are like variables but with a significant difference: their values cannot be changed after they are defined. Constants are used to store values that should remain the same throughout your PHP script.(PHP, ধ্রুবকগুলি ভেরিয়েবলের মতো কিন্তু একটি উল্লেখযোগ্য পার্থক্য সহ: তাদের মানগুলি সংজ্ঞায়িত করার পরে পরিবর্তন করা যায় না। আপনার পিএইচপি স্ক্রিপ্ট জুড়ে একই থাকা উচিত এমন মানগুলি সংরক্ষণ করতে ধ্রুবকগুলি ব্যবহার করা হয়।)

==**Defining Constants:**== Constants are defined using the define() function or the `const` keyword. The **define()** function is typically used for defining global constants, while the `const` keyword is used for class constants.

```php
// Using define() for global constants 
define("SITE_NAME", "My Website"); 
define("MAX_LOGIN_ATTEMPTS", 3); 
// Using const for class constants 
class MathConstants { 
const PI = 3.14159265359; 
}
```
**Accessing Constants:** You can access constants in the same way you access variables, but without the dollar sign ($) before the constant name.

```php
echo SITE_NAME; // Outputs: My Website 
echo MAX_LOGIN_ATTEMPTS; // Outputs: 3 
echo MathConstants::PI; // Outputs: 3.14159265359
```