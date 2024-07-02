#### Naming Convention

**Create a new Table**

```
php artisan make:migration create_users_table
```

**Adding a New Column:**

```
php artisan make:migration add_email_to_users_table 
```

**Update a New Column like rename column**

```
php artisan make:migration update_columnName_to_tableName 
```

**Removing a Column:**

```
php artisan make:migration remove_age_from_users_table --table=users
```

**Renaming a Column:**

```
php artisan make:migration rename_username_to_user_name_in_users_table --table=users
```

**Renaming a Column:**

```
php artisan make:migration deop_tableName
```