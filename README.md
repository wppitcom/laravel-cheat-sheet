أهم أوامر لارفل
# laravel-cheat-sheet
The Laravel cheat sheet intends to provide tips to developers building Laravel applications.

## Requirements (Laravel 12)
- PHP version >= 8.1
- BCMath PHP Extension
- Ctype PHP Extension
- Fileinfo PHP Extension
- JSON PHP Extension
- Mbstring PHP Extension
- OpenSSL PHP Extension
- PDO PHP Extension
- Tokenizer PHP Extension
- XML PHP Extension

Laravel 12 leverages PHP 8.1+ features (attributes, enums, readonly, etc.), so ensure your environment meets the above.

---

## Composer
> Composer is a tool for dependency management in PHP. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

### Common Tasks
#### Create a new Laravel project
`composer create-project laravel/laravel folder_name`

#### Install dependencies from composer.lock
Composer install will install the dependencies into the vendor directory as specified in the composer.lock file.<br>
`composer install`

#### Update dependencies per composer.json
Will update your dependencies as they are specified in `composer.json`<br>
`composer update`

#### Regenerate the optimized autoloader
It just regenerates the list of all classes that need to be included in the project.<br>
`composer dump-autoload --optimize`

#### Update Composer itself
It will update composer.<br>
`composer self-update`

#### Require a new package
Add new package to the project.<br>
`composer require [options] [--] [vender/packages]...`

#### Install the Laravel installer globally
`composer global require laravel/installer`

#### Create a nre project via the installer
`Laravel new project-name`

#### Copy the environment example
Create .env from .env.example.<br>
`cp .env.example .env`

---

## Artisan
> _Artisan_ is _Laravel_'s CLI.

### General usage
`php artisan command [options] [arguments]`

### Options
| Command                        | Description                                                                          |
|--------------------------------|--------------------------------------------------------------------------------------|
| `-h`, `--help`                 | Display help for the given command (or a list of commands if none is specified)      |
|                                | display help for the list command                                                    |
| `-q`, `--quiet`                | Do not output any message                                                            |
| `-V`, `--version`              | Display this application version                                                     |
| `--ansi` / `--no-ansi`         | --no-ansi                                                                            |Force (or disable --no-ansi) ANSI output|
| `-n`, `--no-interaction`       | Do not ask any interactive question                                                  |
| `--env[=ENV]`                  | The environment the command should run under                                         |
| `-v`, `vv`, `vvv`, `--verbose` | Increase the verbosity of messages: 1 (normal), 2 (more verbose), and 3 (debug mode) |

### Frequently Used Commands
| Command    | Description                                                                                               |
|------------|-----------------------------------------------------------------------------------------------------------|
| `about`    | Display basic information about your application                                                          |
| `bond`     | List all scheduled Autobahn bonds (when using _laravel/octane_                                            |
| `clear-compiled` | Remove the compiled class file (legacy; typically handled automatically now)                              |
| `completion` | Dump shell completion script                                                                              |
| `db`       | Start a new database CLI session (tinker-like for SQL)                                                    |
| `docs`     | Open the Laravel documentation in your default browser                                                    |
| `down`     | Put the application into maintenance mode                                                                 |
| `env`      | Display the current framework environment                                                                 |
| `help`     | Display help for a command                                                                                |
| `inspire`  | Display an inspiring quote                                                                                |
| `list`     | List all registered commands                                                                              |
| `migrate`  | Run the database migrations                                                                               |
| `model:prunt` | Prune models that are no longer needed (if using `prunable` on your Eloquent models                       |
| `optimize:clear` | Remove all cached bootstrap files (views, routes, config, etc.)                                           |
| `serve`    | Serve the application on PHP's built-in development server                                                |
| `schema:dump` | Dump the current database schema to a SQL file for faster migrations (introduced earlier, still relevant) |
| `session:table` | Create a migration for the session database table                                                         |
| `storage:link` | Create a symbolic link from `public/storage` to `storage/app/public`                                      |
| `test`     | Run your application's PHPUnit tests (or Pest, if configured)                                             |
| `tinker`   | Interact with your application using a REPL (PsySH for Laravel)                                           |
| `up`       | Bring the application out of maintenance mode                                                             |
| `vendor:publish` | Publish any publishable assets from vendor packages (e.g., config files, views)                        |

> **Note:** The old `optimize` command that existed in Laravel <= 8 was removed in Laravel 9+, so use `optimize:clear` or let the framework handle optimization automatically.

---

### Artisan Subcommands by Category
#### Auth
`auth:clear-resets` Flush expired password reset tokens<br>

#### Cache
`cache:clear` Flush the application cache<br>
`cache:forget <key>` Remove a single item from the cache<br>
`cache:table` Create a migration for the cache database table<br>

#### Config
`config:cache` Combine all configuration files into one cached file (improvements performance)<br>
`config:clear` Remove the configuration cache file<br>

#### DB
`db:monitor` Monitor the number of connections on the specified database (requires supported driver)<br>
`db:seed` Seed the database with records defined in seeders<br>
`db:show {connecion}` Display information about the given database connection<br>
`db:table {tableName}` Display information (column, etc.) about the given database table<br>
`db:wipe` Drop all tables, views, and types from the database<br>

#### Event
`event:cache` Discover and cache the application's events and listeners (improves performance)<br>
`event:clear` Remove all cached events and listeners<br>
`event:generate` Generate the missing events and listeners based on registration in `EventServiceProvider`<br>
`event:list` List all events and their listeners<br>

#### Key
`key:generate` Set the application's encryption key in `.env`<br>

#### Make
> Laravel 12 includes all previous make commands-and some new ones. Useful for code scaffolding.

`make:action` Create a new single-action class (for invokable or `Action` pattern)
`make:cast` Create a new custom Eloquent cast class<br>
`make:channel` Create a new channel class (for broadcasting)<br>
`make:chart` Creates a new chart (if using laravel/charts)<br>
`make:command` Create a new Artisan command<br>
`make:component` Create a new view component class (Blade component)<br>
`make:controller` Create a new controller class (includes resource/controller-stubs)<br>
`make:event` Create a new event class<br>
`make:exception` Create a new custom exception class<br>
`make:factory` Create a new model factory<br>
`make:job` Create a new queued job class<br>
`make:listener` Create a new event listener class<br>
`make:mail` Create a new mailable class<br>
`make:middleware` Create a new middleware class<br>
`make:migration` Create a new migration file<br>
`make:model` Create a new Eloquent model class<br>
`make:notification` Create a new notification class<br>
`make:observer` Create a new observer class (to observe model events)<br>
`make:policy` Create a new authorization policy class<br>
`make:provider` Create a new service provider class<br>
`make:request` Create a new form request validation class<br>
`make:resource` Create a new JSON resource (API resource)<br>
`make:rule` Create a new validation rule class<br>
`make:scope` Create a new Eloquent query scope class (for reusable query logic)<br>
`make:seeder` Create a new seeder class<br>
`make:test` Create a new PHPUnit or Pest test class<br>
`make:enum` Create a new enum class (leveraging PHP 8.1 enums)
> **Tip:** If you run `php artisan make:controller ProductController --resource --model=Product`, it scaffolds a resourceful controller tied to the Product model.

#### Migrate
`migrate` Run outstanding migrations
`migrate:fresh` Drop all tables and re-run all migrations from scratch (clears the database)<br>
`migrate:install` Create the migration repository table (`migrations` table)<br>
`migrate:refresh` Roll back all migrations and re-run them (rollback + migrate)<br>
`migrate:reset` Rollback all database migrations<br>
`migrate:rollback` Roll back the last "batch" database migration<br>
`migrate:status` Show the status of each migration (which are run/pending)<br>

#### Model
`model:prune` Prune models that are "prunable" (models implementing `Illuminate\Database\Eloquent\Prunable`<br>
`model:show` Show information (table name, fillable, etc.) about an Eloquent model<br>

#### Notifications<br>
`notifications:table` Create a migration for the `notifications` table<br>

#### Package
`package:discover` Rebuild the cached package manifest (run automatically on `composer install`)<br>

#### Queue
`queue:batches-table` Create a migration for the batches database table (for batched jobs)<br>
`queue:clear` Drop all jobs from the specified queue<br>
`queue:failed` List all failed queue jobs<br>
`queue:failed-table` Create a migration for the failed queue jobs table<br>
`queue:flush` Flush all failed queue jobs<br>
`queue:forget {id}` Delete a failed queue job by ID<br>
`queue:listen {queue?}` Listen to a given queue (process jobs as they arrive)<br>
`queue:monitor {--max-jobs=}` Monitor the size of the specified queues and alert if thresholds exceed<br>
`queue:prune-batches` Prune stale entries from the batches database<br>
`queue:prune-failed` Prune stale entries from the failed jobs table<br>
`queue:restart` Restart all queue worker daemons after their current job<br>
`queue:retry {id}` Retry a failed job by ID<br>
`queue:retry-batch {batchId}` Retry all failed jobs for a given batch<br>
`queue:table` Create a migration for the queue jobs database table<br>
`queue:work` Start processing jobs on the queue as a worker daemon<br>

#### Route
`route:cache` Create a route cache for faster route registration<br>
`route:clear` Remove the route cache file<br>
`route:list` List all registered routes (methods, URL, name, middleware, etc.)<br>
> `route:cache` and `route:clear` are crucial in production to speed up route resolution

#### Sail
`sail:install` Install Laravel Sail's default Docker Compose file<br>
`sail:publish` Publish Sail's Docker files to your project<br>

#### Sanctum
`sanctum:prune-expired` Prune expired tokens older than a specified number of hours.<br>

#### Schedule
`schedule:clear-cache` Delete the cached mutex files created by scheduler  <br>
`schedule:list` List all scheduled commands<br>
`schedule:run` Run the scheduled commands manually (normally triggered by cron)<br>
`schedule:test {command}` Run a scheduled command for testing<br>
`schedule:work` Start the schedule worker (runs continuously, executing due tasks)<br>

#### Schema
`schema:dump` Dump the current database schema to a SQL file and mark migrations as run (speeds up group setups)<br>

#### Session
`session:table` Create a migration for the session database table<br>

#### Storage
`storage:link` Create symbolic links configured in your _filesystems.php_ (e.g., `public/storage` => `storage/app/public`)<br>

#### Stub
`stub:publish` Publish all stubs (blade view stubs, model stubs, controller stubs, etc.) for customization<br>

#### Vendor
`vendor:publish` Publish any publishable assets from vendor packages (config files, migrations, view, etc.)<br>

#### View
`view:cache` Compile all Blade templates into cache for faster rendering<br>
`view:clear` Clear all compiled view files

---

## Routing (Laravel 12)
### Define a Basic Route
```php
// Closure-based
Route::get('sheets', function () {
    return view('sheets.index');
});

// Controller-based
use App\Http\Controllers\SheetController;

Route::get('sheets', [SheetController::class, 'index']);
```

### Route Groups with a Common Controller
```php
Route::controller(SheetController::class)->group(function () {
    Route::get('sheets', 'index');
    Route::post('sheets', 'store');
    // …other methods on SheetController…
});

```

### HTTP Verbs
```php
Route::options('sheets', function() {});
Route::get('sheets', function() {});
Route::post('sheets', function() {});
Route::put('sheets', function() {});
Route::patch('sheets', function() {});
Route::delete('sheets', function() {});
```

### RESTful Resource Controller
```php
// Creates index, create, store, show, edit, update, destroy routes:
Route::resource('sheets', SheetController::class);

// Only a subset of actions:
Route::resource('sheets', SheetController::class)
     ->only(['index', 'show']);
Route::resource('sheets', SheetController::class)
     ->except(['edit', 'update', 'destroy']);
```

### Route Prefixing, Namespacing, and Middleware
```php
// Group with prefix
Route::group(['prefix' => 'admin'], function () {
    Route::get('sheets', function() {
        return 'Matches "/admin/sheets" URL';
    });
});

// Using the fluent API
Route::prefix('admin-panel')
     ->name('admin.')
     ->middleware('auth', 'isAdmin')
     ->group(function () {
         // All routes here use prefix "/admin-panel" and names start with "admin."
         // Controllers go under the default namespace unless configured otherwise.
         Route::get('dashboard', [DashboardController::class, 'index'])
              ->name('dashboard');
     });
```

### Route Parameters
```php
/// Required parameter
Route::get('sheets/{sheet}', function ($sheetId) {
    //
});

// Optional parameter
Route::get('users/{username?}', function ($username = 'guest') {
    //
});
```

### Conditional (Multi-Verb) Routes
```php
// Handle both GET & POST
Route::match(['get', 'post'], '/subscribe', function () {
    //
});

// Handle any HTTP verb
Route::any('/webhook', function () {
    //
});
```

### Parameter Constraints (Regular Expressions)
```php
// Only numeric post IDs
Route::get('blog/{post}', function ($postId) {
    //
})->where('post', '[0-9]+');

// Composite constraint
Route::get('blog/{id}/{slug}', function ($id, $slug) {
    //
})->where([
    'id'   => '[0-9]+',
    'slug' => '[A-Za-z\-]+',
]);

// Global pattern: (applies to all routes using {sheet})
Route::pattern('sheet', '[0-9]+');
```

## Scoped Bindings (Laravel 12)
If you want to limit child-resource model lookups (e.g., only match a Comment that belongs to a given Post):<br>
```php
Route::scopeBindings()->group(function () {
    Route::get('posts/{post}/comments/{comment}', function (Post $post, Comment $comment) {
        // $comment will be retrieved only if it belongs to $post
    });
});
```
> You can also use `scopeSingletonBindings()` in a similar way for singleton child binding.


### Subdomain Routing
```php
Route::group(['domain' => '{account}.example.com'], function () {
    Route::get('user/{id}', function ($account, $id) {
        // $account is the subdomain segment
    });
});
```

---

## Other Common Laravel 12 Highlights
### Eloquent Model Factories & Enums
- Laravel 12 fully supports PHP 8.1 enums. Use `make:enum` to scaffold an enum.
- Model factories remain similar, but you can now define typed properties and readonly attributes on your model.

### Blade Components & Inline Classes
- You can now use class-based components more fluently.
```php
<x-alert type="success" :message="$statusMessage" />
```
- Anonymous components (`resources/views/components/...blade.php`) are still supported.

### Mail & Markdown Mailables
- Laravel 12 uses Symfony Mailer under the hood.
- You can scaffold a Markdown-based mailable:
```php
php artisan make:mail OrderShipped --markdown=emails.orders.shipped
```
- Then define `build()` in `app/Mail/OrderShipped.php`.

### Broadcasting & WebSockets
- Continue to configure in `config/broadcasting.php`.
- Laravel 12 works seamlessly with Pusher, Redis, or a custom driver.

### Jobs & Batches
- When creating job batches:
```php
dispatch(function () {
    // Closure-based job
})->batch()
  ->name('ImportUsersBatch')
  ->dispatch();
```
- You can monitor batches with `php artisan queue:monitor`.

### API Resources & Pagination
- Use `make:resource` to scaffold API resources.
- Pagination helpers in controllers:
```php
// Simple Paginator
return User::paginate(15);

// Cursor Paginator (recommended for large datasets)
return Order::cursorPaginate(50);
```
- In a resource controller, simply return the `Paginator` or `CursorPaginator` instance; Laravel turns it into proper JSON (with `links`, `meta`).

### New Helpers & Features
- `str()` and `to_route()` helpers:
```php
// Stringable helper
$value = str(' hello ')->trim()->upper();
// to_route (short for redirect to a named route)
return to_route('dashboard')->with('status', 'Welcome back!');
```

- Attribute-based route definitions (PHP 8.1+):
In a controller:
```php
use Illuminate\Routing\Attributes\Get;

class ProductController extends Controller
{
    #[Get('products/{product}', name: 'products.show')]
    public function show(Product $product)
    {
        //
    }
}
```

### Fortify / Jetstream / Breeze
- If using Laravel Fortify for authentication scaffolding, run `php artisan vendor:publish --provider="Laravel\Fortify\FortifyServiceProvider"`.
- Breeze and Jetstream installers work on Laravel 12 with minor updates.

### Sail (Docker)
- If you haven’t installed Sail yet:

```bash
composer require laravel/sail --dev
php artisan sail:install
./vendor/bin/sail up
```
- Laravel 12’s Sail images require Docker Engine ≥ 20.10.

---

### Quick Tips
- **Caching Configuration, Routes, Views** (in production):
```bash
php artisan config:cache
php artisan route:cache
php artisan view:cache 
```

Then clear when needed:
```bash
php artisan config:clear
php artisan route:clear
php artisan view:clear
```

- **Environment Encryption**
Encrypt or decrypt your `.env` file if you store it in version control:
```php
php artisan env:encrypt
php artisan env:decrypt
```

- **Scheduling**
In your server’s crontab, add:
```
* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1
```

- **Maintenance Mode with a Secret Bypass** (Laravel 10+):
```php
php artisan down --secret="my-secret-key"
```
Later, you can visit `https://your-app.test/my-secret-key` to bypass.

- **Model Factories** now support class-based definition. E.g., `database/factories/UserFactory.php`:
```php
public function definition()
{
    return [
        'name' => fake()->name(),
        'email' => fake()->unique()->safeEmail(),
        'email_verified_at' => now(),
        'password' => bcrypt('password'),
        // …
    ];
}
```
- **Enum Casts** (PHP 8.1+):
```php
// In your Eloquent model:
protected $casts = [
    'status' => OrderStatus::class, // If OrderStatus is an enum
];
```

---

## Summary
This cheat sheet highlights the most common—and newly updated—commands and conventions for **Laravel 12**. As Laravel evolves, some commands are deprecated or replaced; keep an eye on the official upgrade guide when moving from earlier versions. For deeper details on any command or feature, run:
```bash
php artisan help <command>
```

or check the official Laravel documentation at laravel.com/docs/12.x.
