<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Chapter 1: Create a new application using play</a>

**Goal:** In this chapter you will learn how to create a play app using the command line.  We will also show you the basic structure of a play application.

## Create a new play application

  You can use the *play* command to create a new application for you, using a standard structure (just like other build tools like Maven).  Play actually uses a build tool called Simple Build Tool (SBT). 
  
  When you create a new play application, it creates a new folder with the name you specify as part of the command.  So change to a suitable folder that is not already under version control or part of any other project, eg *~/projects*. 
  
  Then use the command line to create a new play application called *todolist* using the command:
  
    play new todo-app

  The Play tool will ask you if you want to create either a Scala or Java application. In this case choose to create a Java application project template.

<a href="images/01x01-play-new-todo-app.png"><img src="images/01x01-play-new-todo-app.png" width="640"></a>


## Anatomy of a Play application

  The play new command creates a new directory todo-app with the following structure:

  `app` contains the application’s core, split between models, controllers and views directories. This is the directory where .java source files live.

  `conf` contains all the application’s configuration files, especially the main application.conf file, the routes definition files and the messages files used for internationaligzation.

  `project` contains the build scripts. The build system is based on sbt. But a new play application comes with a default build script that will just works fine for our application.

  `public` contains all the publicly available resources, which includes JavaScript, stylesheets and images directories.

  `test` contains all the application tests. Tests can be written as JUnit tests.

  To understand the structure in more depth, please see the official documentation on the [Anatomy of a Play application](http://www.playframework.com/documentation/2.1.0/Anatomy)


## Run the play application

  Once you have an application created, you can run the Play console. Go to the todo-app folder that has been created for your project and run the command:

        play

  This launches the Play console and it reads the configuration of your Play project. 

<a href="images/01x02-play-console.png"><img src="images/01x02-play-console.png" width="640"></a>
  
  There are several things you can do from the Play console, but lets start by running the application. From the *Play console prompt*, type run:

        [todo-app] $ run


<a href="images/01x03-play-console-run-app.png"><img src="images/01x03-play-console-run-app.png" width="640"></a>

  Now the application is running in development mode. Open a browser at [http://localhost:9000/](http://localhost:9000/)

<a href="images/01x04-play-app-running-in-browser.png"><img src="images/01x04-play-app-running-in-browser.png" width="640"></a>


  If you have a conflict on port 9000, you can change the port play runs on using the play console.  In the console, use the following command to run on port 9999:
  
    [todo-app] $ run 9999

  Now your play application will run from port 9999 from within the Play console.
  

## Play development mode

  Your application is running in development mode with the auto-reload feature enabled.  Each request you make to your Play app will check your project and recompile any sources that have changed. If needed the application will restart automatically.

  If there are any compilation errors you will see the result of the compilation directly in your browser.

<a href="images/01x05-play-error-page.png" width="640"><img src="images/01x05-play-error-page.png" width="640"></a>

[Back to top...](#top)

[Back to Workshop Home](/index.html)

