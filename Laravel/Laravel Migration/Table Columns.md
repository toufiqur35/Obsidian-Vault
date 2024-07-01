### Table Columns

Laravel provides a variety of column types that you can use within your migrations. Here are some of the most commonly used:

- `$table->bigIncrements('id');`: Auto-incrementing UNSIGNED BIGINT (primary key) equivalent column.
- `$table->bigInteger('votes');`: BIGINT equivalent column.
- `$table->binary('data');`: BLOB equivalent column.
- `$table->boolean('confirmed');`: BOOLEAN equivalent column.
- `$table->char('name', 100);`: CHAR equivalent column with an optional length.
- `$table->date('created_at');`: DATE equivalent column.
- `$table->dateTime('created_at', 0);`: DATETIME equivalent column (with precision).
- `$table->decimal('amount', 8, 2);`: DECIMAL equivalent column with precision and scale.
- `$table->double('amount', 8, 2);`: DOUBLE equivalent column with precision and scale.
- `$table->enum('status', ['new', 'pending', 'completed']);`: ENUM equivalent column.
- `$table->float('amount', 8, 2);`: FLOAT equivalent column with precision and scale.
- `$table->integer('votes');`: INTEGER equivalent column.
- `$table->ipAddress('visitor');`: IP address equivalent column.
- `$table->json('options');`: JSON equivalent column.
- `$table->jsonb('options');`: JSONB equivalent column (PostgreSQL).
- `$table->longText('description');`: LONGTEXT equivalent column.
- `$table->macAddress('device');`: MAC address equivalent column.
- `$table->mediumInteger('votes');`: MEDIUMINT equivalent column.
- `$table->mediumText('description');`: MEDIUMTEXT equivalent column.
- `$table->morphs('taggable');`: Adds INTEGER taggable_id and STRING taggable_type.
- `$table->nullableMorphs('taggable');`: Adds nullable versions of the above.
- `$table->softDeletes();`: Adds a deleted_at column for soft deletes.
- `$table->string('email');`: VARCHAR equivalent column.
- `$table->text('description');`: TEXT equivalent column.
- `$table->time('sunrise', 0);`: TIME equivalent column (with precision).
- `$table->timestamp('added_on', 0);`: TIMESTAMP equivalent column (with precision).
- `$table->timestamps(0);`: Adds nullable created_at and updated_at columns with precision.

