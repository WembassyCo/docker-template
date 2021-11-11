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

## Accessing the Sites
- Drupal/Wordpress: localhost:80
- PHPMyAdmin: localhost:81
- Maillog: localhost:82

You can also run terminus from the command line, terminus is often needed for Pantheon
based projects.  To do this run ./pantheon from this templates root folder.
