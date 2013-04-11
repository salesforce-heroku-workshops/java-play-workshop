<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Chapter 3: Deploy your application on Heroku </a>

  Now you know your app is working locally, lets upload it to Heroku so we can show it off to the world.  The world wont see it until you tell it the website address though :)

  1. Create a new heroku application in the route of the project folder

    heroku create

  You should get an output similar to the following (although you will have a uniue name for your heroku app):

    $ heroku create
    Creating damp-sands-1586... done, stack is cedar
    http://damp-sands-1586.herokuapp.com/ | git@heroku.com:damp-sands-1586.git
    Git remote heroku added

  You will notice that a new remote repository called heroku has been added to your git settings, this is the address of the git repository at Heroku you will upload to in order to deploy your code.  To check this you can use the command:
  
    git remote -v

  You can also choose to specify a specific name for your application.  The name you use forms part of the website address (name.herokuapp.com), so that name has to be unique across all Heroku applications.

    heroku create my-unique-app-name


  2. Upload your project to Heroku using a standard git push

    git push heroku master

  Your project will now be securely coppied to the Heroku repository associated with your application and this will trigger the building, deploying and running of your application automatically.

  The first time you deploy your project, your build file will be used to download all the project dependencies (external libraries), so it may take a few moments to complete.

  Heroku will automatically recognise you have uploaded a Java Play framework and will know how to run it.  If you make any changes to the default way play runs, eg. by adding different data sources then you will need to specify a Procfile to define how the application should run.  Writing a Procfile will be covered soon.

  3. Check your application is running on Heroku

  At any time you can open your application by loging into the heroku website and viewing your apps.  You can also open the specific application you are working on via the command line.  In your project folder, use the command:

    heroku open



[Back to top...](#top)

[Back to Workshop home](/index.html)

