# Shuut Documentation

## About

**S**(heffield) **H**(allam) **U**(niversity) **UT** - pronounced shoot(*verb; to move in a particular direction very quickly and directly*), 
is being built as part of my Object Oriented Programming university module.

My goal was to produce a simple web application that could help a courier firm manage it's business, from tracking assets such as drivers and vehicles, through to calculating journey distance, producing quotes and then managing the resulting job through to the invoice stage.

## Getting started with this project

### Requirements

* PHP 7.2 or higher;
* [Composer](https://getcomposer.org/)
* [Yarn](https://yarnpkg.com/en/docs/install#debian-stable)

### Installation
 
#### Clone the repo               
To get started with the installation of this project, first clone the repository:

```bash
git clone https://github.com/rickwest/shuut.git
```

#### Install dependencies
Then install the dependencies:

```bash
composer install
```

#### Install JavaScript dependencies and build the assets
Followed by the installation of the javascript dependencies:

```bash
yarn install
```

You can then build the projects assets:
```bash
yarn run encore dev
```


#### Configure a database
Next, you need to configure and create a database. 

Open the `.env` file and find the line `DATABASE_URL=mysql://db_user:db_password@127.0.0.1:3306/db_name`. 

Replace this with your own database credentials or alternatively, for an SQLite database, use: 

```text
DATABASE_URL=sqlite:///%kernel.project_dir%/var/data.db
```

**Whilst in `.env` you should also add your Google Maps Api key, by adding the line:**

```text
GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

#### Create the database
Now you have configured the database connection you can create the database by running:

```bash
bin/console doctrine:database:create
```

#### Update the schema
Now you have a database, update the schema:

```bash
bin/console doctrine:schema:update --force
```

#### Load the fixtures
This project comes with some demo data that can be loaded using the command:

```bash
bin/console doctrine:fixtures:load
```


#### Authentication
As well as populating the database with demo data, the fixtures command also creates a user.
Log in to the system wih these credentials:

**username: admin**

**password: 20E!xI&$Zx**

### Usage

If you've got this far then you should be all set and ready to run the application. You can [configure a web server](https://symfony.com/doc/current/cookbook/configuration/web_server_configuration.html) like Nginx or Apache
but the easiest thing to do in development is simply run PHP's built in web server:

 ```bash
 bin/console server:run
 ```

This should enable you to access <http://localhost:8000> in your browser. Navigate to `http://127.0.0.1:8000/login` and sign in with the credentials above.

### Demo
![](https://i.imgur.com/T2bT42Y.gif)

### Support
If you need some help or want to ask anything just drop me an [email](mailto:b7042643@my.shu.ac.uk).