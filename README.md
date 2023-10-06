# Tips and Tricks
PHP, Laravel, Javaascript tips and tricks and Tech in general

#### Eloquent & Query builder
Eloquent wherehas 
```php
// basic usage of whereHas()
$user = App\Models\User::where('name', 'john')->first();

$post = App\Models\Post::whereHas('user', function($query) user($user){
    $query->where('id', $user->id);
})->get();
```
More info 
1. [Artical by Muhammad Azeem](https://www.golinuxcloud.com/laravel-eloquent-wherehas/)

#### Database
1. [Database Transactions in Laravel **by Fideloper**](https://fideloper.com/laravel-database-transactions)

#### Linux (Ubuntu)
   
#### Others
1. [GitHub markdown docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

   