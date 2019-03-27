### Invokable Controllers
From Laravel 5.6.28 - if you want to create a controller with just one action, you can use <b>__invoke()</b> method and even create "invokable" controller.

```
<?php
namespace App\Http\Controllers;
use App\User;
use App\Http\Controllers\Controller;
class ShowProfile extends Controller
{
    /**
    * Show the profile for the given user.
    *
    * @param int $id
    * @return Response
    */
    public function __invoke($id)
    {
        return view('user.profile', ['user' => User::findOrFail($id)]);
    }
}
```
Routes:
```
Route::get('user/{id}', 'ShowProfile');
```
Artisan command to generate this controller:
```
php artisan make:controller ShowProfile --invokable`
``
