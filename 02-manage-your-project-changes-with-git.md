
# <a id="chapter2">Chapter 2: Manage project changes with Git</a>

  When developing software it saves so much time and hassel when you version your code.  Using distributed version control systems like Git allow you to collaborate a lot more effectively too.  You can share specific changes you are making across branches and repositories.  When using a service like Github you can also collaborate and run code reviews via pull requests.

## Version the code with Git

  A git client was added when you installed the Heroku Toolbelt.  So now you need to put your project under version control and create a local repository.

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
