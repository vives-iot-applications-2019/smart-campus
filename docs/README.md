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

