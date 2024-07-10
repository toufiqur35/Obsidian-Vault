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

* The whereNot and orWhereNot methods may be used to negate a given group of query constraints. 
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

* The whereBetween method verifies that a column's value is between two values . 

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereBetween('price', [1,100])->get();
	
	return $result;
}
```

* The whereNotBetween method verifies that a column's value lies outside of two values. 

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereNotBetween('price', [1,100])->get();
	
	return $result;
}
```

* The whereBetweenColumns method verifies that a column's value is between the two values of two columns in the same table row. 

```php
public function demoAction()
{
	$patients = DB::table('patients')
			->whereBetweenColumns('weight', ['minimum_allowed_weight', 'maximum_allowed_weight'])
			->get();
	
	return $patients;
}
```
* The whereNotBetweenColumns method verifies that a column's value lies outside the two values of two columns in the same table row.

```php
public function demoAction()
{
	$patients = DB::table('patients')
			->whereNotBetweenColumns('weight', ['minimum_allowed_weight', 'maximum_allowed_weight'])
			->get();
	
	return $patients;
}
```

* The whereIn method verifies that a given column's value is contained within the given array. 

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereIn('price', [20,5000])->get();
	
	return $result;
}
```

* The whereNotIn method verifies that the given column's value is not contained in the given array. 

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereNotIn('price', [20,2000])->get();
	
	return $result;
}
```

* The whereNull method verifies that the value of the given column is NULL.

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereNull('price')->get();
	
	return $result;
}
```

* he whereNotNull method verifies that the column's value is not NULL. 

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereNotNull('price')->get();
	
	return $result;
}
```

* The whereDate method may be used to compare a column's value against a date.

```php
public function demoAction()
{
	$result = DB::table('brands')
	->whereDate('created_at', '2016-12-31')->get();
	
	return $result;
}
```

* The whereMonth method may be used to compare a column's value against a specific month. 

```php
public function demoAction()
{
	$result = DB::table('products')
	->whereMonth('updated_at', '11')->get();
	
	return $result;
}
```

* The whereDay method may be used to compare a column's value against a specific day of the month.

```php
public function demoAction()
{
	$result = DB::table('brands')
	->whereDay('created_at', '22')->get();
	
	return $result;
}
```

* The whereYear method may be used to compare a column's value against a specific year.

```php
public function demoAction()
{
	$result = DB::table('brands')
	->whereDay('created_at', '2022')->get();
	
	return $result;
}
```

* The whereTime method may be used to compare a column's value against a specific time. 

```php
public function demoAction()
{
	$result = DB::table('brands')
	->whereDay('created_at','=', '11:20:45')->get();
	
	return $result;
}
```

* The whereColumn method may be used to verify that two columns are equal.

```php
public function demoAction()
{
	$result = DB::table('brands')
	->whereColumn('updated_at','>', 'created_at')->get();
	
	return $result;
}
```


### Ordering, Grouping, Limit 

#### The `orderBy` Method
* The `orderBy` method allows you to sort the results of the query by a given column. The first argument accepted by the `orderBy` method should be the column you wish to sort by, while the second argument determines the direction of the sort and may be either `asc` or `desc`:

```php
public function demoAction()
{
	$result = DB::table('brands')->orderBy('brandName', 'desc')->get();
	
	return $result;
}
```

#### The `latest` and `oldest` Methods
* The `latest` and `oldest` methods allow you to easily order results by date. By default, the result will be ordered by the table's `created_at` column. Or, you may pass the column name that you wish to sort by:

```php
public function demoAction()
{
	$result = DB::table('brands')->latest()->first();
	
	return $result;
}
```

#### The `inRandomOrder` Methods
* The `inRandomOrder` method may be used to sort the query results randomly. For example, you may use this method to fetch a random user:

```php
public function demoAction()
{
	$result = DB::table('brands')->inRandomOrder()->first();
	
	return $result;
}
```

#### The `groupBy` and `having` Methods
* As you might expect, the `groupBy` and `having` methods may be used to group the query results. The `having` method's signature is similar to that of the `where` method:
* when error -> config/`database.php`/ strict => false

```php
public function demoAction()
{
	$result = DB::table('products')
			->groupBy('price')
			->having('account_id', '>', 100)
			->get();
	
	return $result;
}
```


#### The `skip` and `take` Methods
* You may use the `skip` and `take` methods to limit the number of results returned from the query or to skip a given number of results in the query:

```php
public function demoAction()
{
	$result = DB::table('products')->skip(10)->take(5)->get();
	
	return $result;
}
```

#### The `limit` and `offset` Methods
* Alternatively, you may use the `limit` and `offset` methods. These methods are functionally equivalent to the `take` and `skip` methods, respectively:

```php
public function demoAction()
{
	$result = DB::table('products')->offset(10)->limit(5)->get();
	
	return $result;
}
```


## Insert Statements

* The query builder also provides an `insert` method that may be used to insert records into the database table. The `insert` method accepts an array of column names and values:

```php
public function demoAction()
{
	$result = DB::table('brands')->insert([
		'brandName' => 'new brand',
		'brandImg' => 'image path'
	]);

	return $result;
}
```

## Update Statements

* In addition to inserting records into the database, the query builder can also update existing records using the `update` method. The `update` method, like the `insert` method, accepts an array of column and value pairs indicating the columns to be updated. The `update` method returns the number of affected rows. You may constrain the `update` query using `where` clauses:

```php
public function demoAction()
{
	$result = DB::table('products')
			->where('id', 1)
			->update(['PRICE' => 1000]);

	return $result;
}
```

### Update or Insert Statements
* `updateOrInsert` method may be used. to update an existing record in the database or create it if no matching record exists.

```php
public function demoAction()
{
	$result = DB::table('brands')->updateOrInsert(
		//check data exist or not
		[
			'brandName' => 'Hatil'
		],
		// if data !exist then insert data
		[
			'brandName' => 'new Hatil',
			'brandImg' => 'new image path'
		]
	);

	return $result;
}
```


### Increment and Decrement
* The query builder also provides convenient methods for incrementing or decrementing the value of a given column. Both of these methods accept at least one argument: the column to modify. A second argument may be provided to specify the amount by which the column should be incremented or decremented:

```php
public function demoAction()
{
	//increment
	$result = DB::table('products')
			->where('id', 1)
			->increment('price',10);

	//Decrement
	$result = DB::table('products')
			->where('id', 1)
			->decrement('price',10);

	return $result;
}
```

## Delete Statements
* The query builder's `delete` method may be used to delete records from the table. The `delete` method returns the number of affected rows. You may constrain `delete` statements by adding "where" clauses before calling the `delete` method:
* If you wish to `truncate` an entire table, which will remove all records from the table and reset the auto-incrementing ID to zero, you may use the `truncate` method:

```php
public function demoAction()
{
	//delete statement remove single records from the table 
	$result = DB::table('products')
			->where('id', 1)
			->delete();

	//truncate statement remove all records from the table 
	$result = DB::table('products')
			->where('id', 1)
			->truncate();
			
	return $result;
}
```

### Paginate 
* Display simple "Next" and "Previous" links in your application's UI, use the `simplePaginate` method to perform a single, efficient query.

```php
public function demoAction()
{
	$result = DB::table('products')->simplePaginate(5);
			
	return $result;
}
```

* The paginate method counts the total number of records matched by the query before retrieving the records from the database.

```php
public function demoAction()
{
	$result = DB::table('products')->paginate(5);
			
	return $result;
}
```

* Custom Paginate

```php
public function demoAction()
{
	$result = DB::table('products')->paginate(
				$perPage = 15, $columns = ['*'], $pageName = 'users'
				);	
					
	return $result;
}
```

