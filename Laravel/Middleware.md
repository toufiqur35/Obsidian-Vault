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