# How deploy
## Update the .gitignore
This is necessary because:
>- When you are in Local you use the environment var in local  you connect to your ddb in local
>- When you Make Push you use the environment defined in your server deploy 

```gitignore
*
!.gitignore
.env    <- Add this line
```


## Create a file call (Procfile)
This file do not have extension
```
web: php artisan migrate --force && php artisan serve --host=0.0.0.0 --port=$PORT

```

## Update your /config/database.php
```php
'mysql' => [
            'driver' => 'mysql',
            'url' => env('DATABASE_URL'),
            'host' => env('DB_HOST', '127.0.0.1'),
            'port' => env('DB_PORT', '3306'),
            'database' => env('DB_DATABASE', 'forge'),
            'username' => env('DB_USERNAME', 'forge'),
            'password' => env('DB_PASSWORD', ''),
            'unix_socket' => env('DB_SOCKET', ''),
            'charset' => 'utf8mb4',
            'collation' => 'utf8mb4_unicode_ci',
            'prefix' => '',
            'prefix_indexes' => true,
            'strict' => true,
            'engine' => null,
            'options' => extension_loaded('pdo_mysql') ? array_filter([
                PDO::MYSQL_ATTR_SSL_CA => env('MYSQL_ATTR_SSL_CA'),              // this line is very important
            ]) : [],
        ],
```

## Update your /app/Providers/AppServiceProvider.php

```php
namespace App\Providers;

use Illuminate\Support\ServiceProvider;
use Illuminate\Support\Facades\Schema; // Añade esta línea
class AppServiceProvider extends ServiceProvider
{

    public function register(): void {}

    public function boot(): void
    {
        Schema::defaultStringLength(191); // Añade esta línea
    }
}

```
