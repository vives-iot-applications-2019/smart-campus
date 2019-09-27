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

>`Route::resource('rooms', 'RoomController');`

This single route declaration creates multiple routes to handle a variety of actions on the resource. The generated controller will already have methods stubbed for each of these actions, including notes informing you of the HTTP verbs and URIs they handle.

You may register many resource controllers at once by passing an array to the resources method:

>`Route::resources(['rooms' => 'RoomController']);`
