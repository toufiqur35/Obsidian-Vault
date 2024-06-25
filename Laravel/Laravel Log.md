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

```php
//DemoController.php

function DemoAction(Request $request){
	$sum=$request->num1+$request->num2;
	Log::info($sum);
	Log::emergency($sum);
	Log::alert($sum);
	Log::critical($sum);
	Log::error($sum);
	Log::warning($sum);
	Log::notice($sum);
	Log::debug($sum);
	return $sum;
}


//output 
//log file
[2024-06-25 15:19:55] local.info: any_value
[2024-06-25 15:19:55] local.emergency: any_value
[2024-06-25 15:19:55] local.alert: any_value
[2024-06-25 15:19:55] local.critical: any_value
[2024-06-25 15:19:55] local.ERROR: any_value

```