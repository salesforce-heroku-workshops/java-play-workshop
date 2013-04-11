<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Chapter 1: Create a new application using play</a>

Goal: In this chapter you will learn how to instantly deploy an application on Heroku using the Heroku Toolbelt.  You will also learn how to run the new application locally, make changes, and synchronize the changes with Heroku.  Then you will learn how to instantly scale your application, set configuration parameters through environment variables, and view your application's log entries.

## Create a new play application

  1. On the command line enter: `play new todolist`

  The Play tool will ask you a few questions. Choose to create a simple Java application project template.

  The play new command creates a new directory todolist/ as follows:

    `app` contains the application’s core, split between models, controllers and views directories. This is the directory where .java source files live.

    `conf` contains all the application’s configuration files, especially the main application.conf file, the routes definition files and the messages files used for internationalization.

    `project` contains the build scripts. The build system is based on sbt. But a new play application comes with a default build script that will just works fine for our application.

    `public` contains all the publicly available resources, which includes JavaScript, stylesheets and images directories.

    `test` contains all the application tests. Tests can be written as JUnit tests.


* Run the play application

  Once you have an application created, you can run the Play console. Go to the new todolist/ directory and run:

        $ play

  This launches the Play console. There are several things you can do from the Play console, but let’s start by running the application. From the console prompt, type run:

        [todolist] $ run

  Now the application is running in development mode. Open a browser at [http://localhost:9000/](http://localhost:9000/)


[Back to top...](#top)

[Back to Workshop Home](/index.html)

