# android-project-assistant-cli
A Unix-like shell script which helps you to manipulate Android project, including migrating legacy project, cleaning and listing files.


What Is It
==========
APAC (Android Project Assistant Command-line) is a shell script, you can use it to:

* Migrate a legacy Android project to be Android Studio compatible.
* Clean build files like **bin/**, **gen/**, **build/** etc.
* Clean Gradle cache (**.gradle/**) and/or the Gradle Wrapper.
* Clean Eclipse project files or Android Studio project files.
* List the files like ***.apk**, ***.aar**, ***.jar** in your project directory.

License
=======
Apache License, Version 2.0

How to Run It
=============
After the installation, open a console, enter the directory, then run like this (take Cleaning Build Files for example):

```
MyApp $ apac clean -by
Plan to delete the following in CURRENT and SUB directories:
Directories:
   bin, gen, build
Done.
MyApp $
```

Installation
============
Installing APAC is pretty simple, just copy it to a directory which is part of your **$PATH**.

Or, you can run this command to download the latest APAC script to your **~/bin/** directory (assumes it is part of your $PATH, and **wget** is available):

```
wget https://raw.githubusercontent.com/konca/android-project-assistant-cli/master/src/apac -O ~/bin/apac
```

APAC Help Info
==============

Brief Help Info
---------------
```
MyApp $ apac
usage: apac [-h | --help] <command> [<args>]

Commands:
  help          Show this message
  clean (cl)    Clean temporary or project files etc
  list (ls)     Find files of specified types
  migrate (mg)  Migrate legacy project to Android Studio format or more
```

Help Info of Cleaning
---------------------
```
MyApp $ apac clean
apac clean - Clean the files in specified types in CURRENT and SUB directories.

Usage: apac clean <-bceswTyh>
  -b   Build temporary files, including:
          bin/, gen/, build/
  -c   Cache files, including:
          .gradle/
  -e   Eclipse project files and build files, including:
          project.properties, local.properties,
          .project, .classpath, .settings/,
          bin/, gen/
  -s   Android Studio project files and build files, including:
          *.iml, local.properties, .idea/,
          build/, .gradle/
  -w   Gradle Wrapper files, including:
          gradle/ in current directory
  -T   Total, means **ALL** the directories and files listed above.
  -y   Answer and skip the confirmation.
  -h   Help, show this message
```

Help Info of Listing
--------------------
```
MyApp $ apac ls
apac list - List the files in specified types in CURRENT and SUB directories.

Usage: apac list <-ajrbh>
  -a   APK files
  -j   JAR files
  -r   AAR files
  -b   Bundle files, including APK, AAR, JAR files
  -h   Help, show this message
```