* Sessions provide a way to store information about the user across multiple requests.

```php
// store data temporary

    function SessionPut(Request $request)

    {

        $email = $request->email;

        $request->session()->put('userEmail',$email);

        return true;

    }

  

    // store data select or Retrieving

    function SessionPull(Request $request)

    {

        $request->session()->pull('userEmail',$email);

        return true;

    }

  

    // store data delete only one

    function Sessionforget(Request $request)

    {

        $request->session()->forget('userEmail',$email);

        return true;

    }

    // store data all delete

    function SessionFlush(Request $request)

    {

        $request->session()->flush('userEmail',$email);

        return true;

    }
```

```php
Route::get('/storaged-data/{email}',[DemoController::class,'SessionPut']);

Route::get('/retrieving-data',[DemoController::class,'SessionPull']);

Route::get('/deleting-data',[DemoController::class,'Sessionforget']);

Route::get('/flush-data',[DemoController::class,'Sessionflush']);
```