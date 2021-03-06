# Installation

## Starting a New Project

The best way to start a *project* is to base it on a already available project *distribution*. There are distributions for general web projects or for projects that require an micro-framework style approach.
Distributions come with a predefined app [file structure](../architecture/file-structure), some boilerplate code and the bundled core library.

We'll base our new project off the officially supported [standard distribution](https://github.com/UnionOfRAD/framework).

For the start we'll use [composer](https://getcomposer.org/) to create our project in
the current directory as `project`.

```bash
composer create-project --prefer-dist unionofrad/framework project
```

## Pedal to the Metal

For the purposes of this guide, we'll be using PHP's builtin development webserver. This is good for development but should of course not be used in production. Instructions on how to use other
webservers in production can be found on the [Web-Servers](web-servers) page.

### Permissions

The framework will need write access to the `app/resources/tmp` as it used to store cached versions of
already compiled templates or logs. The webserver user must be able to write to this directory.

### Starting the Webserver

Make sure you are in the root of the project. Now start PHP's builtin webserver using the following command. Your project is then being served at 127.0.0.1 on port 8080.

```bash
php -S 127.0.0.1:8080 -t app/webroot index.php
```

Finally, pull up the project in your browser and visit [`http://127.0.0.1:8080`](http://127.0.0.1:8080).
At this point, you should be presented with the default home page. **You're up and running!**


## Livin' on the Edge

The methods described in the previous sections will download the most recent tagged version of
the framework and core library. In some cases, it may be desirable to update both to the very
latest available revision, which may not have been tagged yet.

```bash
composer create-project -s dev unionofrad/framework project

cd project
git checkout 1.0

cd libraries/lithium
git checkout 1.0
```

