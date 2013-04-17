<link href="index.css" rel="stylesheet" type="text/css">

# Chapter 5: Setting up your IDE

  You do not need to use an IDE such as Eclipse, InteliJ or Netbeans for this workshop, however the Play framework can help you if wish to do so.

  Play can generated project files for some of the common developer tools and integrated developer environments (IDE).

  Using the play console you can generated the required project files.  Please note that if you make significant changes to your project you may have to re-generated these project files.  


## Eclipse

  The Play framework provides a command to generate a project configuration for Eclipse.  This transform a Play application into a working Eclipse project.  
  
  You can either run `play eclipse` or open the play console with the command `play` and use the eclipse command:

    [todo] $ eclipse

  If you want to grab the available source jars (this will take longer and it’s possible a few sources might be missing):

    [todo] $ eclipse with-source=true


  Then import the application into your Workspace with the **File/Import/General/Existing project…** menu (compile your project first).

<a href="images/05x01-play-eclipse-project.png"><img src="05x01-play-eclipse-project.png"></a>

### Using JPDA

  You can also start your application with play debug run and then you can use the Connect JPDA launcher using Debug As to start a debugging session at any time. Stopping the debugging session will not stop the server.

  *Tip: You can run your application using ~run to enable direct compilation on file change. This way scala template files are auto discovered when you create a new template in view and auto compiled when the file changes. If you use normal run then you have to hit Refresh on your browser each time.*

  If you make any important changes to your application, such as changing the classpath, use eclipse again to regenerate the configuration files.

  *Tip: Do not commit Eclipse configuration files when you work in a team!*

  The generated configuration files contain absolute references to your framework installation. These are specific to your own installation. When you work in a team, each developer must keep his Eclipse configuration files private.

## InteliJ



## Netbeans




[Back to top...](#top)

[Back to Workshop home](/index.html)
