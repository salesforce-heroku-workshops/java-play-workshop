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
  
  When you deploy your application, you use a secure shell (SSH) connection to Heroku.  This SSH connection requires you to add a public key (RSA key) to your Heroku account. deploy applications your need to add you public key to Heroku.  This identifies you to Heroku using the email address you used when creating your account.  If you create your own key, it is therefore important to ensure that the public key has your email as a comment.

  When you run `heroku login` to connect to Heroku it will detect any public key you already have and upload it to Heroku.  If you do not have a public key then one will be created for you.




## Java SE 6 or greater:

  1. As you are developing a Java application, you need the Java Development Kit (JDC) which has the command for the Java compiler `javac`.  Check you have java and javac installed using the following commands:

    $ java -version
    java version "1.6.0_37"
    Java(TM) SE Runtime Environment (build 1.6.0_37-b06-434-10M3909)
    Java HotSpot(TM) 64-Bit Server VM (build 20.12-b01-434, mixed mode)

    $ javac -version
    javac 1.6.0_27


  If you do not have javac then you need to download the Java Standard Edition JDK from Oracle:
  
  [http://www.oracle.com/technetwork/java/javase/downloads/index.html](http://www.oracle.com/technetwork/java/javase/downloads/index.html)



## Download & install Play framework version 2:

     [Download Play 2 framework](http://www.playframework.com/download)

Download the latest 2.0 RC version and extract the archive to a location where you have both read and write access.  For example, create a ~/apps/play folder and extract the archive there.

*(Play updates files within its own folder, so don’t install to /opt, /usr/local or anywhere else you’d need special permission to write to.)*

## Configure Play

  1. Add the folder you extracted Play framework into onto the system PATH.

  **Linux and MacOSX:**

  Add the following text to the file `~/.profile`

    `export PATH=$PATH:/path/to/play20`

  Load this updated PATH into your command line using `source ~/.profile` or open a new terminal window.

  **Microsoft Windows**
  
  Windows uses a global environment variable. Update the PATH in the environment variables to add the path to the Play framework folder, ensure you don’t use a path with spaces. Open a new terminal to make sure the path has been updated.

  2. On Linux & MacOSX, make sure that the play script is executable, otherwise do a `chmod a+x play`

  3. Test play is working by running `play help` on the command line

<a href="images/00x01-play-help-first-run-output.png"><img src="images/00x01-play-help-first-run-output.png" align="middle" width="640"></a>

  When you first run play it may download extra libraries that it needs to run, so you may need to be connected to the Iternet.
  
  Assuming everything went okay, you are ready to create your first Play application.

[Back to top...](#top)

[Back to Workshop home](/index.html)

