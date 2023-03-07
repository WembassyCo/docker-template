## Introduction
This is meant as a template so that you can get started quickly with any drupal
or wordpress project on your local machine.  You should have 1 instance of this template
for each project you will work with.

## Getting Started

You will need to make sure you have a few tools installed on your system
in order for this to work, they are as follows:

- git
- docker

## How to start a new project
You will need a datbase backup file to import, and you will need to clone your project's
repository from github, pantheon, or acquia to somewhere on your machine.

You will need to copy the .env.example file to the .env file. Go through the .env file
you just created and update the settings it asks you to.

After you have finished updating you .env file from this folder run:
docker-compose up

Once it has completed you will see a log of the server, additionally you need to keep this window
open or the server will be closed.

## Database Connection Details
For setting the database connection details for your drupal installation the settings.php or settings.local.php files 
database connection should look like the following:

```php
 $databases['default']['default'] = array (
    'database' => $envs['DB_NAME'] ?? 'mysql',
    'username' => $envs['DB_USER'] ?? 'root',
    'password' => $envs['DB_PASSWORD'] ?? 'password',
    'prefix' => '',
    'host' => $envs['PROJECT_NAME'] ? $envs['PROJECT_NAME'] . '_mariadb' : 'localhost',
    'namespace' => 'Drupal\\Core\\Database\\Driver\\mysql',
    'driver' => 'mysql',
  );
```

## Accessing the Sites, these are default but can be chanced in the .env file
- Drupal/Wordpress: localhost:81
- PHPMyAdmin: localhost:82
- Maillog: localhost:83

# Using Drush with the project
Use the included bash command, drush or manually use:
docker exec ${PROJECT_NAME}_apache drush status

# Using Terminus with the project
You can also run terminus from the command line, terminus is often needed for Pantheon
based projects.  There is a included bash command called terminus that will allow for this

