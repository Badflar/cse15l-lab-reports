## CSE15L Lab Reports (Spring 2022)

# Lab Report 1 W2
This lab report will cover how to log into the course specific "ieng6" remote computer.

## Part 1 Installing Visual Studio Code
This step is not necessary as the terminal on Windows is the same exact thing but having the editor is also a nice thing to have. 

First navigate to [Visual Studio Code Download Page](https://code.visualstudio.com/download)

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20105918.png?raw=true)

Pick the correct installer for your opererating system and run the installer. Leave the default options in the installer.
If successful you should now have Visual Studio Code installed. 

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20110518.png?raw=true)

Don't worry if your Visual Studio Code looks a bit different. You might have a "welcome" window for being a new user. 

## Part 2 Remotely Connectiong
Before we can connect to our machine, we need to enable OpenSSH on our Windows computer. Most have it enabled by default however you can check on [this website](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) using the "Install OpenSSH using Windows Settings" section.

The second thing you need is your username and password for your machine. You should've gotten an email about reseting your password for labs. This will be your password. To get the username, nagivate to [Account Lookup](https://sdacs.ucsd.edu/~icc/index.php), plug in your username and student ID and you should be presented with your username.

Note: if you're currently enrolled in multiple classes that provide lab computers make sure to pick the one with "15l" in the name. 

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20111701.png?raw=true)

Now we can connect.

Open VS Code and open the terminal ("CTRL + `" or use Terminal > New Terminal). Write the following command but replace zzz with the last three letter in your username (these are the characters uniqiue to you).

```markdown
ssh cs15lsp22zzz@ieng6.ucsd.edu
```

Since this is the first time you are logging in using your machine, you are likley to get a message like this: 

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20114705.png?raw=true)

Type ```yes``` and press enter. Rerun the previous ssh command and then enter your password. When typing your password, you will notice that no characters come up. This is normal and is used for security reasons. Press enter and you should get something that looks like this:

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20115258.png?raw=true)


Congratulations! You have successfully logged into your remote machine! 

# Part 3 Trying Some Commands

You might notice something about your remote machine. Theres no UI. In fact the only way to interact with your remote machine as of right now is a command line. Here are some basic commands to get you started.

1. ```cd```

```cd``` stands for "change directory" and allows you to navigate the file system in your computer. 
Usage:
- ```cd``` or ```cd ~``` will put the user in their home directory.
- ```cd dir``` will put the user in a subdirectory of the curent directory. For example if the user is in ```/Desktop/CSE12```, ```cd PA1``` will put the user in ```/Desktop/CSE12/PA1```.
- ```cd ..``` will move the user up one directory. So if the user is in ```/Desktop/CSE12/PA2``` and runs ```cd ..``` they will be moved to ```/Desktop/CSE12```.
- ```cd -``` will put the user in the previously in directiory.

Tip: if you know a file or folder exists but don't know how to spell it exactly, you can start typing the file name and press tab to cycle through the directory.

2. ```ls```

```ls``` stands for "list" and lists all the directories in the folder.

3. ```pwd```

```pwd``` stands for "print working directory" and displays the path name of the working directory.
![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20123013.png?raw=true)

4. ```mkdir```

```mkdir``` stands for "make directory" and creates one or more new directories.
Usage:
- ```mkdir Test``` creates a new directory called "Test" in the current working directory.
- ```mkdir /home/linux/ieng6/cs15lsp22/cs15lsp22zzz/Test``` creates a new directory called "Test."

5. ```cp```

```cp``` stands for "copy" and it copies files.
Usage:
- ```cp hello.java hello.txt``` will copy "hello.java" as "hello.txt" in the same directory. If "hello.txt" already exists, the file will be overwritten.
- ```cp myProject /home/linux/ieng6/cs15lsp22/cs15lsp22zzz/"``` copies "myProject" from the working directory to "/home/linux/ieng6/cs15lsp22/cs15lsp22zzz".

# Part 4 Moving Files with ```scp```

Obviously working through a command line interface is a bit of a pain and would be very difficult to create programs with. We would want to figure out a way to copy files from our work copmuter to our remote computer. So lets explore that.

Create a file on your personal computer titled "WhereAmI.java" and put the following code inside:

```java
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

**Before preceeding, exit your remote computer by running ```exit```**

Then in your terminal in the directory where your new file is saved, run the following command:

```
scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/
```

After entering your password you will notice that not a whole lot happened... 

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20135936.png?raw=true)

However if we log back into our remote computer and run ```ls``` we will notice that our file has been copied.

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20140149.png?raw=true)

And if you were to run ```javac WhereAmI.java``` then ```java WhereAmI``` you should see the infomation of your remote computer.  

# Part 5 Setting an SSH Key

Now so far it might seem tedious to have to enter your password over and over even though you are using the same personal computer to connect. To make things easier we are going to create an SSH Key so you no longer need to enter a password for the computer you are currently using. 

On your personal computer run:

```ssh-keygen```

```Enter File in which to save the key (/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa```

```Enter passphrase (empty for no passphrase):```

```Enter same passphrase again:```

If sucessful you should have sometihng like this:

![Image](https://github.com/Badflar/cse15l-lab-reports/blob/main/Screenshots/Lab1/Screenshot%202022-04-06%20141159.png?raw=true)

Now we need to copy the *public* key to the .ssh directoy to the server computer.

```ssh cs15lsp22zzz@ieng6.ucsd.edu```

*enter password*

```mkdir .ssh```

```exit```

```scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zzz@ieng6.ucsd.edu:~/.ssh/authorized_keys```

*enter password*

Once you are done you should be able to ```ssh``` or ```scp``` from the client. 

# Part 6 Optimize Remote Running

Here are a few tips for making command line work easier

- You can write quotes around the end of an ssh login command to immediately run a new command on the server. For example:
  ```ssh cs15lsp22aci@ieng6.ucsd.edu "ls"```
- You can make semicolons to run multiple commands in order. For example:
  ```cp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI```
- You can use the up arrow on your keyboard to recall previous commands.
- You can use tab to predictive type your directory search. 
