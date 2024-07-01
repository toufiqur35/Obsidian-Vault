Laravel migrations also allow you to add indexes and foreign keys to your tables. Here’s how you can do that:

```php
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

class AddIndexesToUsersTable extends Migration
{
    public function up()
    {
        Schema::table('users', function (Blueprint $table) {
            $table->index('email'); // Simple index
            $table->unique('email'); // Unique index
            $table->primary('id'); // Primary key
        });
    }

    public function down()
    {
        Schema::table('users', function (Blueprint $table) {
            $table->dropIndex(['email']); // Drop index
            $table->dropUnique(['email']); // Drop unique index
            $table->dropPrimary(['id']); // Drop primary key
        });
    }
}

```