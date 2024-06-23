### 1. Create a new Laravel project

```php
composer create-project laravel/laravel example-app
laravel new example-app
```
### 2. Configure the database
The next step is to configure the database for your application.

```mysql
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=database name
DB_USERNAME=root
DB_PASSWORD=
```

### 3. Install `Api`

```
php artisan install:api
```

### 3. Add `HasApiTokens` to the User models
app\\http\\model\\`User.php`

```php
use Laravel\Sanctum\HasApiTokens;

class User extends Authenticatable
{
    use HasFactory, Notifiable, HasApiTokens;
}
```

### 4. Create Database Table

```
//you can create any name of table

php artisan make:migration create_products_table
```
* configuration table
```php
Schema::create('products', function (Blueprint $table) {
   $table->id();
   $table->string('name');
   $table->string('price');
   $table->string('description');
   $table->timestamps();
});
```
### 5. Migrate to database

```
php artisan migrate
```
### 6. Create the Model

```
php artisan make:model Product
```
* open this Product model file
* app\\http\\model\\`Product.php`

```php
protected $table = 'products';
protected $fillable = [
	'name',
	'price',
	'description',
    ];
```

### 7. Create the controller
* With controllers, you can group related request handling logic within a single class. In a Laravel project, controllers are located in the app/Http/Controllers directory.

```
php artisan make:controller Api/ProductController
```

#### Configuration Controller File

```php
namespace App\Http\Controllers\Api;
use App\Http\Controllers\Controllers;
use Illuminate\Http\Request;
use App\Models\Product;
use App\Http\Resourece\ProductResourece;

class ProductController extends Controller
{
	public function index()
    {
		$products = Product::get();

		if($products->count()>0){
		return ProductResource::collection($product);
		}
		else{
		return response()->json(['message'=>'No record available'], 200);
		}
    }

	public function store(Request $request)
    {
	$validated = $request->validate([
		'name' => 'required|max:255',
		'price' => 'required|intiger',
		'description' => 'required',
		]);
    }

	public function show(Procutc $product)
    {
	
    }

	public function update(Request $request, Procutc $product)
    {
	
    }

	public function destroy(Procutc $product)
    {
	
    }
}
```

### Creating Resource
To generate a resource class, you may use the `make:resource` Artisan command. By default, resources will be placed in the `app/Http/Resources` directory of your application. Resources extend the `Illuminate\Http\Resources\Json\JsonResource` class:

```
php artisan make:resource ProductResource
```

* app \\http\\Resource\\`ProductResource.php`

```php
namespace App\Http\Resources;
use Illuminate\Http\Request;
use Illuminate\Http\Resources\Json\JsonResource;
class ProductResource extends JsonResource
{

public function toArray(Request $request): array
	{
		return [
		'id' => $this->id,
		'name' => $this->name,
		'price' => $this->price,
		'description' => $this->description,
		'created_at' => $this->created_at,
		'updated_at' => $this->updated_at,
		];
	}
}
```
### 7. Create the `Api` Routes

```
Route::apiResource('products',ProductController::class);
```
* check this resources route list
```
php artisan route:list
```
* resources `api` routes list
```
GET|HEAD   api/products ........... product.index > Api\ProductController@index
POST   api/products ........... product.store > Api\ProductController@store
GET|HEAD   api/products/{product} ....... product.show > Api\ProductController@show
PUT|PATCH   api/products/{product} .. product.update > Api\ProductController@update
DELETE   api/products/{product} ... product.destroy > Api\ProductController@destroy
```