<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Setting up your environment</a>

  Before you get started developing the application you will deploy on Heroku, you need to have an Heroku account, have install the Heroku toolbelt and a working Internet connection to Heroku.

## Create an Heroku Account (if you dont already have one)

  You can create a free account at the Heroku website.  You need an account in order to deploy and manage the applications on Heroku.

  1. In your browser navigate to: [https://heroku.com/signup](https://heroku.com/signup)
  2. Enter your email address
  3. Select `Sign Up`
  4. Check your email and navigate to the verification page
  5. Enter a suitable password for your account


## Installing the Heroku Toolbelt

  The Heroku toolbelt is a command line application for creating and managing your applications on Heroku.  Its a really useful tool.  The toolbelt also contains a Git client, although you can use your own Git client if you prefer.
  
  When you created your account, the Heroku website directs you to download the Heroku toolbelt.  It is available from the [Heroku toolbelt website](http://toolbelt.heroku.com) if you do not have it on your development machine.
  
  Install the Heroku toolbelt version for your operating system.  You can test it is installed by using the command `heroku` which will list out the Heroku tasks you can do from the command line.


## Setting up secure access to Heroku (public key)
  
  When you deploy your application, you use a secure shell (SSH) connection to Heroku.  This SSH connection requires you to add a public key (RSA key) to your Heroku account.  Your public key identifies you to Heroku using the email address you used when creating your account.  If you create your own key, ensure that the public key has your email as a comment.

  When you run `heroku login` to connect to Heroku it will detect any public key you already have and upload it if possible to Heroku.  If you do not have a public key then heroku will  created for you.



## Java SE 6 or greater (application requirement)

  As you are building a Java pplication you need to have the compiler that comes with the Java Development Kit (JDK) installed.  If you are not sure, you can test the java compiler is installed using the command for the Java compiler:

    $ javac -version
    javac 1.6.0_27


  If the `javac` command is not recognised then download and install Java Standard Edition JDK from Oracle from the following website
  
  [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)


## Download & install Play framework version 2:

   [Download Play 2 framework](http://www.playframework.com/download)

Download the latest version of the Play framework and extract the archive to a location where you have both read and write access.  For example, create a ~/apps/play folder and extract the archive there.

*Note: Play updates files within its own folder, so on MacOSX and Ubuntu avoid installing play in /opt, /usr/local or anywhere else you’d need special permission to write to unless you also update the play folder write permissions.*

## Add Play framework to your executable path

  In order to run play commands from your project folders you should add the folder you extracted Play framework into the system PATH.

  **On Linux and MacOSX:**

  Add the following text to the file `~/.profile`

    `export PATH=$PATH:/path/to/play20`

  Load this updated PATH into your command line using `source ~/.profile` or open a new terminal window.

  Make sure that the play script is executable, otherwise do a `chmod a+x play`
  

  **On Microsoft Windows**
  
  Windows uses a global environment variable. Update the PATH in the environment variables to add the path to the Play framework folder, ensure you don’t use a path with spaces. Open a new terminal to make sure the path has been updated.

## Test Play framework is working

  Test play is configured correctly by running the following command:
  
    play help
  
  When you first run play it may download extra libraries that it needs to run, so you may need to be connected to the Internet.

<a href="images/00x01-play-help-first-run-output.png"><img src="images/00x01-play-help-first-run-output.png" align="middle" width="640"></a>
  
  Assuming everything went okay, you are ready to create your first Play application.

[Next](02-manage-your-project-changes-with-git.html)
[Back to top...](#top)
[Back to Workshop home](index.html)

