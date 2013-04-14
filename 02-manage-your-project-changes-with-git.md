<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Chapter 2: Manage project changes with Git</a>

  When developing software it saves so much time and hassel when you version your code.  Using distributed version control systems like Git allow you to collaborate effectively too.  You can share specific changes you are making across branches and different repositories.  
  
  When using a service like Github you can also collaborate and run code reviews via pull requests.
  

## Version the project with Git

  A git client was added when you installed the Heroku Toolbelt, but you can also use any you have already installed.  
  
  Now you have created your play project, you will use Git to put your project under version control.  This will create a local git repository which is contained within a folder called *.git*.  It is therefore important that you never delete the .git folder as you will loose your version control history.

1. Create (initialise) a new git repository inside your project folder

    cd my-project-folder
    git init


2. Check this worked by viewing the current status of your git repository

    git status

 You should see a list of files that are not currently tracked by git.

3. Add the project files to your git repository & commit the changes:

    git add .
    git commit -m "Initial Java Play project created"


  You should now have a versioned project.  Any changes you now make to these project files can be tracked using *git status*.


[Back to top...](#top)

[Back to Workshop Home](/index.html)
