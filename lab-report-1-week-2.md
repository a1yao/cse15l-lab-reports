# Setting up and logging into a course specific ieng6 account #

## Install VSCode ##
Go to the [Visual Studio Code Website](https://code.visualstudio.com/) and follow the instructions to install VSCode based on your operating system. 

After installing and opening the program, a window like below should show up.

![VSCode](vscode.png)

## Remotely Connecting ##

If you're on a Windows operating system, the first step you need to complete is installing OpenSSH. Follow the steps [here](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse).

Then, use [this link](https://sdacs.ucsd.edu/~icc/index.php) to look up your course-specific ieng6 account. 

Open a terminal in your VSCode and type in the following command: 

```
ssh <course-specific-account-name>
```

Say yes to whatever questions they give you, then enter your password when prompted. The entire process should look something like this:

![login](login.png)

## Trying Some Commands ##

After connecting your terminal to the server, any commands you run on that terminal will run on the server as well. Try running a couple commands like `ls`, `cd`, `mkdir`, and `ls -lat`. 

Below is what happens when I run `ls -lat` in my terminal logged onto my `cs15lsp22` account:

![lsLat](lsLat.png)


