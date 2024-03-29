# WordPress Boilerplate for Professional Development

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#https://gitpod.io/#https://github.com/4GeeksAcademy/wordpress-hello)

1. Dockerfile for a working LAMP environment with PHP 7.2.19 and PHPMyAdmin.
2. WordPress CLI (WP CLI).
3. Support for `.env` file to easily publish into production with environment variables.
4. One commend install with `install.sh` bash script.
5. It comes with a [WordPress Plugin](https://github.com/alesanchezr/wpas-wordpress-dash) ideal for using headless WordPress API working with typical MVC (Model View Controller) pattern.
6. Composer integration to [install plugins](https://wpackagist.org/) or [PHP packages](https://packagist.org/) via package manager.

##### If used with Gitpod
7. Easy access to apache and PHP error log with commcommand: gp open /var/log/apache2/error.log

## Installation Procedure

#### 1) Start by installing the boilerplate

There are 3 ways of installing this:

1. Use the [Breathecode CLI](https://github.com/breatheco-de/breathecode-cli)
```bash
$ bc start:wordpress -r
```
2. Use git
```bash
$ git clone git@github.com:4GeeksAcademy/wordpress-hello.git
```
3. Just [click here](https://gitpod.io/#https://github.com/4GeeksAcademy/wordpress-hello) to use it with gitpod.

#### 2) Install the composer packages
```bash
$ composer install
```

#### 3) Create a .env file with your database and site information (on the workspace root) and run the run the installator
```bash
$ bash install.sh
```

## You are done! Start working!

Check your website, you are going to see a "Hello Rigoberto" message, you can login into the dashboard with your c9 username and the password you specified.

### - Adding API enpoints
This boilerplate comes with a sample API andpoint already, all api enpoints can be added into the **setup_api.php** file like this:
```php
// adding a GET /courses endpoint handled by the function getDraftCourses in the SampleController.php file
$api->get([ 'path' => '/courses', 'controller' => 'SampleController:getDraftCourses' ]);
```
Here is more info on [how to create the API endpoints](https://github.com/alesanchezr/wpas-wordpress-dash/tree/master/src/WPAS/Controller#creating-an-apis-using-mvc).

### - Adding Entities (Post Types)
All the Post Types configuration is done in the **setup_types.php** file like this:

```php
// adding Post Type "Course" handled by the file Course.php
$typeManager->newType(['type' => 'course', 'class' => 'Course'])->register();
```
Here is more info on [how to create the post-types](https://github.com/alesanchezr/wpas-wordpress-dash/tree/master/src/WPAS/Types).

### Connecting to the server:
```
ssh $HOSTGATOR_USER@108.179.232.58 -p2222
```

To restart the agent
```
eval "$(ssh-agent -s)"
```
change key permissions
```
chmod 400 ~/.ssh/keyname
```
To add the key
```
ssh-add <(echo "$HOSTGATOR_SSH")
```