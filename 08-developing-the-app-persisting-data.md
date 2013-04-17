<link href="index.css" rel="stylesheet" type="text/css">

# Developing the app - Persisting the data

  Now we have a Task model, its time to persist the tasks in a database to make the application useful. Lets start by enabling a database in our application. In the **conf/application.conf** file, add:

    db.default.driver=org.h2.Driver
    db.default.url="jdbc:h2:mem:play"

For now we will use a simple in memory database using H2. No need to restart the server, refreshing the browser is enough to set up the database.

We will use EBean (the default Object Relational Model tool for Play framework) in this tutorial to query the database. So you’ll have to enable it in the **conf/application.conf** file as well:

    ebean.default="models.*"

By doing this we create an Ebean server connected to the default datasource, managing all entities found in the models package. Now it’s time to transform our **Task class** to a valid EBean entity:

    package models;

    import java.util.*;

    import play.db.ebean.*;
    import play.data.validation.Constraints.*;

    import javax.persistence.*;

    @Entity
    public class Task extends Model {

      @Id
      public Long id;

      @Required
      public String label;

      public static Finder<Long,Task> find = new Finder(
        Long.class, Task.class
      );

      ...

  We made the Task class extend the `play.db.ebean.Model` super class to have access to Play built-in Ebean helper. We also added proper persistence annotations, and created a find helper to initiate queries.

  Lets implement the CRUD operations:

    public static List<Task> all() {
      return find.all();
    }

    public static void create(Task task) {
      task.save();
    }

    public static void delete(Long id) {
      find.ref(id).delete();
    }

  Now you can play again with the application, creating new tasks should work.


<a href="images/08x01-play-app-creating-tasks.png"><img src="images/08x01-play-app-creating-tasks.png"></a>


  Note: Read more about the [Ebean Object Relational Mapper](http://www.playframework.com/documentation/2.1.0/JavaEbean) in Play framework.

## Deleting tasks

  Now that we can create tasks, we need to be able to delete them. Very simple, we just need to finish the implementation of the deleteTask action:

    public static Result deleteTask(Long id) {
      Task.delete(id);
      return redirect(routes.Application.tasks());
    }

  Now you should be able to delete your tasks as well as add them.


## Commit your changes locally and deploy

  Again as we have made a significant change to the web app functionality, even though its not complete, we should commit those changes to Git.
  
  Add these changes to your local git repository as follows:
  
    git add .
    git commit -m "added Task model, forms and page"

  Push this commit to Heroku to deploy the new version of the code using the command
  
    git push heroku master

  Reload your browser to check the live website has been updated, or use the command `heroku open` 


[Back to Workshop home](index.html)
