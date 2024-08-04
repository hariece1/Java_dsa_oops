

Gettting the id from the url and using in the page
```java
Route::get('/participant/{id}',function($id){

    return 'Hello participant '.$id.' ';

});
```

Redirecting url with naming the url
```java
Route::get('/hari', function() {

    return redirect()->route('renamed');

});
Route::get('/namingroute',function(){

    return 'I am from nameing route';

    })-> name('renamed');
```

Url grouping 
```java
Route::group(['prefix' => 'admin'],function(){

    Route::get('/hari', function() {

        return redirect()->route('renamed');

    });

    Route::get('/participant/{id}',function($id){

        return 'Hello participant '.$id.' ';

});
});

```

Using controller class

```java
//in route 

Route::get('/hari', [Homekey::class,'aboutus']);

//To make controller
php artisan make:controller controllername
//In controller

class Homekey extends Controller
{
    public function aboutus(){
        return redirect()->route('renamed');
    }
}
```