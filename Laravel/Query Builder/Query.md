Laravel's database query builder provides a convenient, fluent interface to creating and running database queries. It can be used to perform most database operations in your application and works perfectly with all of Laravel's supported database systems.

#### [Retrieving All Rows From a Table](https://laravel.com/docs/11.x/queries#retrieving-all-rows-from-a-table)

```php
public function demoAction()
{
$users = DB::table('users')->get();
return $users;
}
```

#### [Retrieving a Single Row / Column From a Table](https://laravel.com/docs/11.x/queries#retrieving-a-single-row-column-from-a-table)

```php
public function demoAction()
{
$user = DB::table('users')->where('name', 'John')->first();
$user = DB::table('users')->find(3);
return $user;
}
```

### [Aggregates](https://laravel.com/docs/11.x/queries#aggregates)

* The query builder also provides a variety of methods for retrieving aggregate values like `count`, `max`, `min`, `avg`, and `sum`. You may call any of these methods after constructing your query:

```php
public function demoAction()
{
$result = DB::table('users')->count();
$result = DB::table('orders')->max('price');
$result = DB::table('orders')->max('price');
return $result;
}
```
