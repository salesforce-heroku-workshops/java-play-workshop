<link href="index.css" rel="stylesheet" type="text/css">

# <a id="top">Setting up your environment</a>

Before you get started you will need to have an account with Heroku, the Heroku toolbelt and a working SSH connection to Heroku:

## Create an Heroku Account (if you dont already have one)
  1. In your browser navigate to: [https://heroku.com/signup](https://heroku.com/signup)
  2. Enter your email address
  3. Select `Sign Up`
  4. Check your email and navigate to the verification page
  5. On the command line, run `heroku login` to connect to Heroku and upload your public key.  If you do not have a public key then one will be created for you.

## Check network (SSH) access to heroku.com
  1. For Linux or MacOSX, either use an SSH client or `telnet` to verify the network connectin by running one of the following in a command prompt / terminal.  On Microsoft Windows you can use a tool called [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html):

            ssh -T heroku.com 22

  2. If the connection is refused then you will need to ask your network administrators to open up SSH access to `heroku.com` (port 22).


## Java SE 6 or greater:

  1. Check wich version of Java you are running on the command line using `java -version`

        $ java -version
        java version "1.6.0_37"
        Java(TM) SE Runtime Environment (build 1.6.0_37-b06-434-10M3909)
        Java HotSpot(TM) 64-Bit Server VM (build 20.12-b01-434, mixed mode)

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

Now that everything is setup you are ready to create your first application on Heroku.

[Back to top...](#top)

[Back to Workshop home](/index.html)

