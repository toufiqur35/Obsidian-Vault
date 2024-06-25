* To help you learn more about what' s happening within your application, Laravel provides robust logging services that allow you to log messages to files

```php
//DemoController.php

function DemoAction(Request $request){
	$sum=$request->num1+$request->num2;
	Log::info($sum);
	return $sum;
}

//output
laravel.log  file
```

* You may write information to the logs using emergency, alert, critical, error, warning, notice, info and debug