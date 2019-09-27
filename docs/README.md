# Smart Campus

The Smart Campus project is a web application that is set up to manage LoRaWAN sensors that are installed in different rooms. The application provides a dashboard that show the current values and history of the following parameters:

* Temperature
* Humidity
* Light
* Motion
* Battery

## Project setup

The project is initialy set up with the following steps.

### Laravel

Create new Laravel project in current directory

```bash
laravel new
```

### Documentation

In order to manage the documentation that is generated while creating and developing this project, Vuepress is used. All documentations resides in the `/docs` directory.

First you need to install Vuepress globally.

```bash
npm install -g vuepress
```

To start the documentation server, run the following command:

```bash
npm run docs:dev
```

## Add roomcontroller

Laravel resource routing assigns the typical "CRUD" routes to a controller with a single line of code. For example, you may wish to create a controller that handles all HTTP requests for "rooms" stored by your application. Using the make:controller Artisan command, we can quickly create such a controller:

```
php artisan make:controller RoomController --resource
```

This command will generate a controller at `app/Http/Controllers/RoomController.php`. The controller will contain a method for each of the available resource operations.

`artisan`

>Artisan is the command-line interface included with Laravel. It provides a number of helpful commands that can assist you while you build your application.


`artisan make:controller`

>Creates a new controller file.

`--resource`

>The controller will contain a method for each of the available resource operations – index(), create(), store(), show(), edit(), update(), destroy().

## Add Room routes resource

Next, you may register a resourceful route to the controller (in `routes/web.php`):

```
Route::resource('rooms', 'RoomController');
```

This single route declaration creates multiple routes to handle a variety of actions on the resource. The generated controller will already have methods stubbed for each of these actions, including notes informing you of the HTTP verbs and URIs they handle.

You may register many resource controllers at once by passing an array to the resources method:

```
Route::resources(['rooms' => 'RoomController']);
```

## Add rooms migration

Migrations are like version control for your database, allowing your team to easily modify and share the application's database schema. Migrations are typically paired with Laravel's schema builder to easily build your application's database schema. If you have ever had to tell a teammate to manually add a column to their local database schema, you've faced the problem that database migrations solve.

To create a migration, use the make:migration Artisan command:

```
php artisan make:migration create_rooms_table
```

The new migration will be placed in your `database/migrations` directory. Each migration file name contains a timestamp which allows Laravel to determine the order of the migrations.

The `--table` and `--create` options may also be used to indicate the name of the table and whether the migration will be creating a new table. These options pre-fill the generated migration stub file with the specified table:

```
php artisan make:migration create_users_table --create=users
php artisan make:migration add_votes_to_users_table --table=users
```

If you would like to specify a custom output path for the generated migration, you may use the `--path` option when executing the `make:migration` command. The given path should be relative to your application's base path.

Example path:

```
database/migrations/2019_09_26_140104_create_rooms_table.php
```

To run all of your outstanding migrations, execute the migrate Artisan command:

```
php artisan migrate
```
