# Resource Controllers

> Laravel resource routing assigns the typical "CRUD" routes to a controller with a > single line of code. For example, you may wish to create a controller that handles all HTTP requests for "photos" stored by your application. Using the make:controller Artisan command, we can quickly create such a controller: <

```bash
$ php artisan make:controller PhotoController --resource
```

> This command will generate a controller at app/Http/Controllers/PhotoController.php. The controller will contain a method for each of the available resource operations. <>

> Next, you may register a resourceful route to the controller:

```bash
Route::resource('photos', PhotoController::class);
```

> This single route declaration creates multiple routes to handle a variety of actions on the resource. The generated controller will already have methods stubbed for each of these actions, including notes informing you of the HTTP verbs and URIs they handle. <>

> You may register many resource controllers at once by passing an array to the resources method: <

```
Route::resources([
    'photos' => PhotoController::class,
    'posts' => PostController::class,
]);
```

### Actions Handled By Resource Controller

| Verb                 | URI                  | Action               | Route Name:          |
|:---------------------|:---------------------|:---------------------|:---------------------|
| GET	               | /photos              |	index	             | photos.index         |
| GET	               | /photos/create	      | create	             | photos.create        |
| POST	               | /photos	          | store	             | photos.store         |
| GET	               | /photos/{photo}	  | show	             | photos.show          |
| GET	               | /photos/{photo}/edit | edit	             | photos.edit          |
| PUT/PATCH            | /photos/{photo}	  | update               | photos.update        |
| DELETE	           | /photos/{photo}	  | destroy	             | photos.destroy       |