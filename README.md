# Tips and Tricks
PHP, Laravel, Javaascript tips and tricks and Tech in general

#### Eloquent & Query builder
###### Eloquent wherehas 
```php
// basic usage of whereHas()
$user = App\Models\User::where('name', 'john')->first();

$post = App\Models\Post::whereHas('user', function($query) user($user){
    $query->where('id', $user->id);
})->get();
```
Read more
1. [Artical by Muhammad Azeem](https://www.golinuxcloud.com/laravel-eloquent-wherehas/)

<br>

#### Collections & Helpers
###### “tap” Method
The `tap` method on a collection allows to "tap" into a collection at a specific point and do something with the result while not affectiong the main/original collection.

Here is an example
```php
$items = [
    ['name' => 'David Charleston', 'member' => 1, 'active' => 1],
    ['name' => 'Blain Charleston', 'member' => 0, 'active' => 0],
    ['name' => 'Megan Tarash', 'member' => 1, 'active' => 1],
    ['name' => 'Jonathan Phaedrus', 'member' => 1, 'active' => 1],
    ['name' => 'Paul Jackson', 'member' => 0, 'active' => 1]
];
```
We can start by changing this array into a collection, add filters and tap into it
```php
return collect($items)
    ->where('active', 1)
    ->tap(function($collection){
        return var_dump($collection->pluck('name'));
    })
    ->where('member', 1)
    ->tap(function($collection){
        return var_dump($collection->pluck('name'));
    });
```
Results #1
```
David Charleston, Megan Tarash, Jonathan Phaedrus, Paul Jackson
```
Result #2
```
David Charleston, Megan Tarash, Jonathan Phaedrus
```
Read more
1. [Laravel New - Laravel Collection “tap” Method](https://laravel-news.com/collection-tap)
2. [tutsforweb - Tap In Laravel](https://tutsforweb.com/tap-in-laravel/)
3. [Taylor Otwell](https://medium.com/@taylorotwell/tap-tap-tap-1fc6fc1f93a6)
4. [Laracast forum](https://medium.com/@taylorotwell/tap-tap-tap-1fc6fc1f93a6)
5. [Freek.dev - Laravel's tap helper function explained](https://freek.dev/694-laravels-tap-helper-function-explained)
<br>
<br>

#### Database
1. [Database Transactions in Laravel **by Fideloper**](https://fideloper.com/laravel-database-transactions)

#### Linux (Ubuntu)
   
#### Others
1. [GitHub markdown docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

   