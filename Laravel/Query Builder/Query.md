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

```
