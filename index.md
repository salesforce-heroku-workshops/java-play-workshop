<link href="index.css" rel="stylesheet" type="text/css">

<a id="top">Heroku Workshop - Java & Play framework</a>
=======================================================

This workshop will give you experience deploying and managing an application on Heroku, an elastic polyglot platform.

In the workshop you will building a relatively simple Java application using the Play framework.  You will version the source code and push your code to Heroku using Git.

For developers, the best way to understand the value of Heroku is to use it in a project.  If you want to know more about the platform, please see the quick [overview of Heroku](what-is-heroku.md) and visit [How it Works]() on the [heroku website](http://www.heroku.com).

The workshop is arranged in the following sections:

* [Chapter 0: Setting up your environment](00-setting-up-your-environment.html)
* [Chapter 1: Get started with your app](01-get-started-with-your-app.html)
* [Chapter 2: Manage your project changes with Git](02-manage-your-project-changes-with-git.html)
* [Chapter 3: Deploy your application on Heroku](03-deploy-your-application-on-heroku.html)
* [Chapter 4: ](#chapter4)
* [Chapter 5: ](#chapter5)
* [Chapter 6: Performance Monitoring with New Relic](#chapter6)
* [Chapter 7: Searching Logs with Papertrail](#chapter7)
* [Appendix A: Where to go next](#appendix-a)


[Back to top...](#top)

[Back to Workshop home](/index.html)



<a id="chapter4">Chapter 4: Developer workflow part 1 - lets get hacking</a>
----------------------------------------------------------------------------

* Modify your project


  1. Let’s make some modifications to the new application. In the Application.java change the content of the response:

    public static Result index() {
      return ok("Hello world");
    }

  With this change, the index action will now respond with a simple text/plain Hello world response. To see this change, just refresh the home page in your browser:

  There is no need to compile the code yourself or restart the server to see the modification. It is automatically reloaded when a change is detected. But what happens when you make a mistake in your code? Let’s try:

    public static Result index() {
      return ok("Hello world);
    }

Now reload the home page in your browser:

[compile error]



<a id="chapter">Chapter : Collaborating on projects</a>
-------------------------------------------------------

As you are using git to version control your project, you can also use it to collaborate with other developers and teams.

* Collaborating via Heroku

  Anyone with an Heroku account can be added to your project as a collaborator.  This will allow them to deploy updates (git push) to your application on Heroku directly.  Collaborators can also see the status of your application, change the resources used and enable or remove addons for your app.

  Anyone who is added as a collaborator should therefore understand their responsibilities, especially if they are added to a prodution application.

  To add a collaborator via the Heroku website:

  1. Visit your appliations on the Heroku website
  2. Go to the `Collaboration` tab
  3. Type in the Heroku account name of the person you want to add.


* Collaborating via Github

  Anyone with a Github account can collaborate, regardless of if they have an Heroku account.  This is a much safer way to collaborate and enables use of Github aspects including pull requests.

  Only one person needs to have an Heroku account to push the changes up to the project.  You can make your Heroku app as collaborative as your developers feel is appropriate.

  To collaborate via Github

  1. Create a new repository on Github
  2. Add any collaborators you wish using their Github account name (or send them a link to your repository, so the can fork it and send you pull requests).
  3. Add this new Github repository to your project, run the following within the top level folder of your project (where .git folder lives):

    git remote add git@github.com:account-name/repo-name


  Using `git log` you can to see the state of the repos you have linked to your local repository.  To make this easier to see, you can configure the output of git log to display the commit log.


![command-line-git-log-commit-graph-image][]

  You can also use a git tool such as Source Tree (MacOSX) to show off the commit graph

![source-tree-commit-graph-image]()





<a id="chapter">Chapter : Adding a staging environment</a>
----------------------------------------------------------

In some situations you will want to test your application as a working website or service before actually deploying it to production.  It is a simple matter to create additional Heroku applications that will work from the same codebase.

  1. Navigate to the root folder of your project, where your .git folder, Procfile and root of your application lives.

  2. Check which addons you are using, as you will want to add these to your other environments.  Either make a note of them or send the output of `heroku addons` to a file

    heroku addons   ; lists addons in the terminal window

    heroku addons > heroku-addons-list.txt    ; copies list of addons to a file


  3. Create a new Heroku app, with a specific name

    heroku create my-unique-app-name-test
    heroku create my-unique-app-name-staging
    heroku create my-unique-app-name-production-support

  There is no specfic naming convention required by heroku, although the above names are commonly used.  Use a naming convention that works for your organisation and try and stick with it to avoid confusion.



<a id="chapter">Chapter : Setting up a staging environment</a>
--------------------------------------------------------------

Some development workflows call for a one or more environments outside production.  Most developers consider their own system the development environment, however a test and staging environments are also very common as applications get bigger and more connected.

It is very easy to create multiple identical environments using heroku, all from within the same project you have already created.

* Create a staging environment

  1. Make sure you are in the root folder of your project
  2. Run the following command to create a new heroku application for staging

    heroku create --



<a id="chapter6">Chapter 6: Performance Monitoring with New Relic</a>
---------------------------------------------------------------------

Goals: With the New Relic Heroku Add-on you can easily setup application performance monitoring and reporting.  This chapter will teach you how to add New Relic to your application.

New Relic provides an in-depth view into the performance and memory usage of applications on Heroku.

Start by adding the New Relic Add-on:

1. Navigate in your browser to [https://addons.heroku.com/newrelic](https://addons.heroku.com/newrelic)
2. Select `Add` for the free "Standard" level of service
3. Select your application from the drop-down
4. Select `+`

Now your application needs to be configured to use the New Relic Java agent:

1. Download the newest New Relic Java Agent zip file from [http://download.newrelic.com/newrelic/java-agent/newrelic-api/](http://download.newrelic.com/newrelic/java-agent/newrelic-api/)
2. Unzip the archive
3. Copy the `newrelic.jar` and `newrelic.yml` files into the root directory of your project

Commit these new files to your Git repository and push the new version to Heroku:


You need to change the default `JAVA_OPTS` environment variable for your application to the Java process to use the New Relic Java agent.

1. In Eclipse, in the `My Heroku Applications` view select the application's context menu
2. Select `App Info`
3. Select the `Environment Variables` tab
4. Select the environment variable with the key of `JAVA_OPTS`
5. Select `Edit`
6. In the `Value` field enter `-Xmx384m -Xss512k -XX:+UseCompressedOops -javaagent:newrelic.jar`
7. Select `OK`

Test the application on Heroku in your browser and verify that it works as expected.

You can now browse the New Relic Dashboard:

1. In your browser navigate to [https://api.heroku.com/myapps](https://api.heroku.com/myapps)
2. Select the application you added New Relic to
3. Select the `Add-ons` drop-down
4. Select `New Relic`

Explore the New Relic dashboard.  (Note: It might take a few minutes for some data to appear in the dashboard.)


[Back to top...](#top)


<a id="chapter7">Chapter 7: Searching Logs with Papertrail</a>
--------------------------------------------------------------

Goals: This chapter will teach you how to add the Paptertrail Heroku Add-on to your application.  Papertrail provides a robust web interface for searching your application's logs and setting alerts for specific searches.

To add the Papertrail Add-on:

1. Navigate in your browser to [https://addons.heroku.com/papertrail](https://addons.heroku.com/papertrail)
2. Select `Add` for the free "Choklad" level of service
3. Select your application from the drop-down
4. Select `+`
5. Open the `Add-ons` drop-down for your application
6. Select `Papertrail`

After a minute or so Papertrail will have your latest logs.

Enter a search term like `WARN` in the search box at the bottom of the screen.  You will then see all of the log entries for your application which match that term.

You can setup Papertrail to notify you via email when new log entries matching your search are received:

1. Select `Save Search`
2. Enter a name for the saved search
3. Select `Save & Setup Alert`
4. Select `Emails`
5. In the `Recipients` field enter your email address
6. Choose a `Frequency`
7. Select `Update`

The next time your application has a log event that matches your search, you will receive an email notification.

[Back to top...](#top)


<a id="appendix-a">Appendix A: Further Learning</a>
-------------------------------------------------

Heroku Basics:

* [How Heroku Works](http://heroku.com/how)
* [Heroku Dev Center](http://devcenter.heroku.com)

Java on Heroku:

* [Java on Heroku Dev Center](https://devcenter.heroku.com/categories/java)
* [Get started with Java on Heroku in your browser](http://java.heroku.com)
* [Heroku Eclipse Plugin](http://eclipse-plugin.herokuapp.com)

Integrating Java with Force.com:

* [Rich SObjects Library](https://github.com/ryanbrainard/richsobjects)
* [Force.com REST API Docs](http://www.salesforce.com/us/developer/docs/api_rest/index.htm)
* [Force.com Developer Resources](http://developer.force.com)

Cloud Application Architecture:

* [12 Factor App](http://12factor.net)


[Back to top...](#top)



Options on this workshop
------------------------

* Adding Twitter bootstrap to the project to create some great UI designs for the site.  It will make the end result more interesting to talk about and allow some more creativity into the workshop.  See the [Twitter Bootstrap site](http://twitter.github.com/bootstrap/)


Other workshop ideas
--------------------
- Open Source project
  ¦-- using github for collaboration, pull request, using travis-ci for running tests with link to pull requests to know that they are safe to merge, using github for issue management, markdown for wiki, creating a markdown site on Heroku



Talks
-----
- polyglot developer, polyglot deployment - most developers are becomeing polyglot developers whether by design or neccessety.  With applications spreading over multiple server, devices, languages and technologies, often the most effective way is to use different tools for different jobs.  So what happens when it comes to deploy all this.  How do you manage to keep it all simple and part of the natural deployment workflow?

Enter the polyglot platform


PDF generation
--------------
Create a bash script that grabs the ruby gem and installs it, then calls the gem to generate the PDF




Resources

http://developer.force.com


forcedotcom developer user groups
http://bit.ly/fdc-dugs

Twitter accounts & hashtags
#forcedotcom
#askforce




    Document Date: January 16, 2013
    Document Home: http://java-play-todo-list.herokuapp.com

