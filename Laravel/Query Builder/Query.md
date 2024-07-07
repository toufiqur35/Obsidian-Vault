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
$result = DB::table('orders')->min('price');
$result = DB::table('orders')->avg('price');
$result = DB::table('orders')->sum('price');
return $result;
}
```

## [Select Statements](https://laravel.com/docs/11.x/queries#select-statements)

* You may not always want to select all columns from a database table. Using the `select` method, you can specify a custom "select" clause for the query:
#### [Select Clause](https://laravel.com/docs/11.x/queries#specifying-a-select-clause)

```php
public function demoAction()
{
$result = DB::table('products')->select('title', 'price')->get();
return $result;
}
```

The `distinct` method allows you to force the query to return distinct results:

```php
public function demoAction()
{
$result = DB::table('products')->select('title')->distinct()->get();
return $result;
}
```

## [Joins](https://laravel.com/docs/11.x/queries#joins)

#### [Inner Join Clause](https://laravel.com/docs/11.x/queries#inner-join-clause)
The query builder may also be used to add join clauses to your queries. To perform a basic "inner join", you may use the `join` method on a query builder instance. The first argument passed to the `join` method is the name of the table you need to join to, while the remaining arguments specify the column constraints for the join. You may even join multiple tables in a single query:

```php
public function demoAction()
{
	$users = DB::table('products')
	->join('categorys', 'products.category_id', '=', 'categorys.id')
	->join('brands', 'products.brand_id', '=', 'brands.id')
	->get();
}
```