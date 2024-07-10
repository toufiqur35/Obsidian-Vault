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

#### Left Join Clause
The `LEFT JOIN` keyword returns all records from the left table (table1), and the matching records from the right table (table2). The result is 0 records from the right side, if there is no match.

```php
public function demoAction()
{
	$users = DB::table('users')
	->leftJoin('posts', 'users.id', '=', 'posts.user_id')	
	->get();
}
```

#### Right Join Clause
The `RIGHT JOIN` keyword returns all records from the right table (table2), and the matching records from the left table (table1). The result is 0 records from the left side, if there is no match.

```php
public function demoAction()
{
	$users = DB::table('users')
	->rightJoin('posts', 'users.id', '=', 'posts.user_id')	
	->get();
}
```

#### Cross Join Clause
The `CROSS JOIN` keyword returns all records from both tables (table1 and table2).

```php
public function demoAction()
{
	$users = DB::table('users')->crossJoin('posts')	->get();
}
```

#### Cross Join Clause
Advanced join clauses in SQL are used to combine rows from two or more tables based on a related column between them. While basic join types like INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL OUTER JOIN are commonly used, advanced join clauses offer more complex and powerful ways to query data. Here are some advanced join clauses and concepts:

```php
public function demoAction()
{
	DB::table('users')
	->join('contacts', function (JoinClause $join) {
	$join->on('users.id', '=', 'contacts.user_id')
	->where('contacts.user_id', '>', 5);
	})
	->get();
}
```

#### Unions Clause
* The union method takes two argument is the first query, and the second argument is the second query.
* The two queries must select the same columns in the same order.
* The `UNION` operator is used to combine the result-set of two or more `SELECT` statements.
- Every `SELECT` statement within `UNION` must have the same number of columns
- The columns must also have similar data types
- The columns in every `SELECT` statement must also be in the same order

```php
public function demoAction()
{
	$query1 = DB::table('products')->where('products.price');
	$query2 = DB::table('products')->where('products.discount','=',1);
	$result = $query1->union($query2)->get();
	return $result;
}
```

## [Basic Where Clauses](https://laravel.com/docs/11.x/queries#basic-where-clauses)

The where() method allows you to filter the results. 12 Laravel Query Builder
* = (equal to) 
* != (not equal to) 
* < (less than) 
* <= (less than or equal to) 
* (greater than) 
* = (greater than or equal to) 
* LIKE (contains)
* NOT LIKE (does not contain) 
* IN (is in the list)
* NOT IN (is not in the list)

```php
public function demoAction()
{
	$result = DB::table('products')->where('products.discount','=',1);
	$result = DB::table('products')->where('products.title', 'like', '%Ca%')->get();
	return $result;
}
```

#### Advance Where Clauses
* The orWhere method to join a clause to the query using the or operator. 
* The whereNot and orWhereNot methods may be used to negate a given group of query constraints. 
* The whereBetween method verifies that a column's value is between two values . 
* The whereNotBetween method verifies that a column's value lies outside of two values. 
* The whereBetweenColumns method verifies that a column's value is between the two values of two columns in the same table row. 
* The whereNotBetweenColumns method verifies that a column's value lies outside the two values of two columns in the same table row.
* The whereIn method verifies that a given column's value is contained within the given array. 
* The whereNotIn method verifies that the given column's value is not contained in the given array. 
* The whereNull method verifies that the value of the given column is NULL.
* he whereNotNull method verifies that the column's value is not NULL. 
* The whereDate method may be used to compare a column's value against a date. 
* The whereMonth method may be used to compare a column's value against a specific month. 
* The whereDay method may be used to compare a column's value against a specific day of the month.
* The whereYear method may be used to compare a column's value against a specific year. 
* The whereTime method may be used to compare a column's value against a specific time. 
* The whereColumn method may be used to verify that two columns are equal.


#### Or Where Clauses
* When chaining together calls to the query builder's `where` method, the "where" clauses will be joined together using the `and` operator. However, you may use the `orWhere` method to join a clause to the query using the `or` operator. The `orWhere` method accepts the same arguments as the `where` method:

```php
public function demoAction()
{
	$result = DB::table('products')
	->where('products.price', '>', 100)
	->orWhere('products.price', '=', 20)->get();
	
	return $result;
}
```

#### Where Not Clauses
* The `whereNot` and `orWhereNot` methods may be used to negate a given group of query constraints. For example, the following query excludes products that are on clearance or which have a price that is less than ten:

```php
public function demoAction()
{
	$result = DB::table('products')
	->where('products.price', '>', 100)
	->whereNot('products.price', '=', 20)->get();
	
	return $result;
}
```

