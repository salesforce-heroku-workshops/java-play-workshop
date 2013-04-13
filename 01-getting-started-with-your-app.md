<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Chapter 1: Create a new application using play</a>

**Goal:** In this chapter you will learn how to create a play app using the command line.  We will also show you the basic structure of a play application.

## Create a new play application

  You can use the *play* command to create a new application for you, using a standard structure (just like other build tools like Maven).  Play actually uses a build tool called Simple Build Tool (SBT). 
  
  When you create a new play application, it creates a new folder with the name you specify as part of the command.  So change to a suitable folder that is not already under version control or part of any other project, eg *~/projects*. 
  
  Then use the command line to create a new play application called *todolist* using the command:
  
    play new todo-app

  The Play tool will ask you if you want to create either a Scala or Java application. In this case choose to create a Java application project template.

  The play new command creates a new directory todolist/ as follows:

    `app` contains the application’s core, split between models, controllers and views directories. This is the directory where .java source files live.

    `conf` contains all the application’s configuration files, especially the main application.conf file, the routes definition files and the messages files used for internationaligzation.

    `project` contains the build scripts. The build system is based on sbt. But a new play application comes with a default build script that will just works fine for our application.

    `public` contains all the publicly available resources, which includes JavaScript, stylesheets and images directories.

    `test` contains all the application tests. Tests can be written as JUnit tests.


## Run the play application

  Once you have an application created, you can run the Play console. Go to the new todolist/ directory and run the command:

        play

  This launches the Play console. There are several things you can do from the Play console, but let’s start by running the application. From the console prompt, type run:

        [todo-app] $ run

  Now the application is running in development mode. Open a browser at [http://localhost:9000/](http://localhost:9000/)


[Back to top...](#top)

[Back to Workshop Home](/index.html)

