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

```php
use Laravel\Sanctum\HasApiTokens;

class User extends Authenticatable
{
    use HasFactory, Notifiable, HasApiTokens;
}
```