* Laravel Blade is a templating engine that comes built-in with the Laravel PHP framework. It allows developers to write clean and structured HTML templates with dynamic content and reusable components. 
* Laravel Blade Blade templates use a combination of plain HTML and special Blade syntax, such as double curly braces {{ }} for variable output and at signs @ for control structures like loops and conditionals. 
* Blade templates can be extended to create a base template that can be reused across multiple pages with different content. 
* Blade also provides several built-in directives that simplify common tasks like including sub views, injecting content into sections, and rendering JSON data.

#### PASS AND DISPLAYING DATA
* Display data that is passed to your Blade views by wrapping the variable in curly braces 
* Blade ' s {{ }} echo statements are automatically sent through PHP' s html special chars function to prevent XSS attacks.

```php
//DemoControler.php

function HomePage1()
    {
        $num1=70;
        $num2=20;
        $sum=$num1+$num2;
        return view('home1',['marks'=>$sum]);
    }
```

```php
//Home.blade.php

<body>
	<h1>Sum is={{$marks}}</h1>
</body>
```