<p align="center"><img src="https://res.cloudinary.com/dtfbvvkyp/image/upload/v1566331377/laravel-logolockup-cmyk-red.svg" width="400"></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/v/stable.svg" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://poser.pugx.org/laravel/framework/license.svg" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

## Requirement
-   PHP >= 7.2.0
-   BCMath PHP Extension
-   Ctype PHP Extension
-   JSON PHP Extension
-   Mbstring PHP Extension
-   OpenSSL PHP Extension
-   PDO PHP Extension
-   Tokenizer PHP Extension
-   XML PHP Extension

## Tools and Extension
 1. Web Server
	 - [Xampp](https://www.apachefriends.org/index.html)
 2. Visual Studio Code
	 - [Laravel Extension Pack](https://marketplace.visualstudio.com/items?itemName=onecentlin.laravel-extension-pack)
	 - [PHP Extension Pack](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-pack)
 3. Postman
	 - [Postman Chrome](https://chrome.google.com/webstore/detail/postman/fhbjgbiflinjbdggehcddcbncdddomop?hl=id)

## Schema Database
  
Visit this page and copy paste the code below in the text editor
[https://www.planttext.com/](https://www.planttext.com/)
```
	@startuml

	hide circle

	entity "members" as e01 {
	  * id : number <<generated>>
	  --
	  * name : string
	  * gender : enum
	  * phone : integer
	  * email : string
	  * address : text
	  --
	  * division_id : unsigned integer <<FK>>
	  * created_at : timestamps 
	  * updated_at : timestamps
	}

	entity "divisions" as e02 {
	  *id : integer <<generated>>
	  --
	  *name : string 
	  -- 
	  * created_at : timestamps 
	  * updated_at : timestamps
	}

	e01 }|..|| e02

	@enduml
```

## Routing
 1. #### Basic Routing
```php
    Route::get('foo', function () {
	    return 'Hello World';
    });
```
 2. #### Available Router Methods
```php
	Route::get($uri, $callback);
	Route::post($uri, $callback);
	Route::put($uri, $callback);
	Route::patch($uri, $callback);
	Route::delete($uri, $callback);
	Route::options($uri, $callback);
```
## Controller
```php
<?php

namespace App\Http\Controllers;

use App\Http\Controllers\Controller;
use App\User;

class UserController extends Controller
{
    /**
     * Show the profile for the given user.
     *
     * @param  int  $id
     * @return View
     */
    public function show($id)
    {
        return response()->json([
	        'message' => 'hallo world'
        ],200);
    }
}
```
## Migration
```php
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

class CreateFlightsTable extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('flights', function (Blueprint $table) {
            $table->increment('id');
            $table->string('name');
            $table->string('airline');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::drop('flights');
    }
}
```
## Model
```php
<?php

namespace App;

use Illuminate\Database\Eloquent\Model;

class Flight extends Model
{
    //
}
```
