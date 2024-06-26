#### Middleware
* Middleware is a special types of controller executed after request but before in response.
* It is a type of filtering mechanism to ensure API Securities and more.
* Middleware acts as a bridge between a request and a response.

![[11-01.png]]
#### Uses of Middleware
* Use to implement API key, user agent restriction, CSRF, XSRF security, token based API authentication.
* Use to implement API Request rate limit.
* Logging of incoming HTTP request.
* Redirecting the users based on request.
* Middleware can inspect a request and decorate it, on reject it, based on what it finds.
* Middleware is most often considered separate from your application logic.
* Middleware give your enough freedom to create your own security mechanism.

#### REQUEST MIDDLEWARE
* Understanding over the middleware structure

```php
namespace App\Http\Middleware;

use Closure;
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Auth;
use Symfony\Component\HttpFoundation\Response;

class AuthenticatedMiddleware
{

   public function handle(Request $request, Closure $next): Response
    {
       return $next($request);
    }
}
```

* Check Request Header Inside Middleware

```php
namespace App\Http\Middleware;

use Closure;
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Auth;
use Symfony\Component\HttpFoundation\Response;

class AuthenticatedMiddleware
{

   public function handle(Request $request, Closure $next): Response
    {
       if(Auth::user()->role != 'admin')
        {
            return redirect('/');
        }
        return $next($request);
    }
}


//route
Route::get('/hello',[DemoController::class,'DemoAction'])->middlewire([DemoMiddlewire::class]);
```

* Apply For Specific Route
```php
Route::get('/hello',[DemoController::class,'DemoAction'])->middlewire([DemoMiddlewire::class]);
```

* Apply For Route Group
```php
Route::middleware(['DemoMiddlewire'])->group(function () {
	Route::get('/hello1',[DemoController::class,'DemoAction1']);
	Route::get('/hello2',[DemoController::class,'DemoAction2']);
	Route::get('/hello3',[DemoController::class,'DemoAction3']);
});
Route::get('/hello',[DemoController::class,'DemoAction']);
```

### [Middleware Aliases](https://laravel.com/docs/11.x/middleware#middleware-aliases)
You may assign aliases to middleware in your application's `bootstrap/app.php` file. Middleware aliases allows you to define a short alias for a given middleware class, which can be especially useful for middleware with long class names:

```php
use App\Http\Middleware\DemoMiddlewire;

->withMiddleware(function (Middleware $middleware) {
$middleware->alias([
'demo' => DemoMiddlewire::class
]);
})
```
* `web.php`
```php
Route::middleware(['Demo'])->group(function () {
	Route::get('/hello1',[DemoController::class,'DemoAction1']);
	Route::get('/hello2',[DemoController::class,'DemoAction2']);
	Route::get('/hello3',[DemoController::class,'DemoAction3']);
});
Route::get('/hello',[DemoController::class,'DemoAction']);
```

* Apply For Whole Application

```php

```