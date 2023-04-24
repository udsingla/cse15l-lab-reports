# Lab Report 1 - Remote Access and FileSystem
## How to login and access remote access on your computer

## Step 1: Installing VScode
Go to the [VScode website](https://code.visualstudio.com/) and follow the instrutions on the website ot download and install it on your device.

Once it is installed, you should be able to open a window that looks like below:
![Image](VScode_img.png)

I had VScode already installed on my laptop so I could skip this step.

## Step 2: Remotely Connecting
If you are on Windows, you need to install `git` for Windows.
You can do that from [Git for Windows](https://gitforwindows.org/).

Once installed, use the steps in this post to set your default terminal
to use the newly-installed `git bash` in Visual Studio Code: \
[Using Bash on Windows in VScode](https://stackoverflow.com/a/50527994)

Then, to use `ssh`, open a terminal in VScode. (Ctrl or Command + \`, or use the Terminal → New Terminal menu option). Your command will look like this, but with the `zz` replaced by the letters in your course-specific account.

`$ ssh cs15lsp23zz@ieng6.ucsd.edu`

Since it is the first time connecting to the server, it asks about the authenticity of host. Type `yes` to connect to the server. However, if it is a server you connect to *often* and you still get this prompt then it means that someone else is trying to access the connection.

Give it your password, and after pressing enter you will be logged in.

The screen should look like: \
![image](logging_in.png)

Now you are successfully connected to the server.

## Step 3: Trying some Commands
Try running the commands `cd`, `ls`, `pwd`, `mkdir`, and `cp` a few times in different ways, both on your computer, and on the remote computer after ssh-ing (use the terminal in VScode).

These commands do the following:
1. `cd` - It stands for Change Directory, using `cd` along with the name of the repository takes you to that repository. `cd` on its own takes you to the home directory. Since we are already on the home directory of the remote server, we do not see a change when we run cd.
2. `cd ~` - It takes us to the home directory as well. The benefit of this over `cd` is that we can follow it with another repository name on the home directory to go directly to it. For example `cd ~/perl5`.
3. `ls <directory>` - I tried ls ~ which lists the contents of the home directory.
4. `cat` - It concatenates the contents of the files given as input and outputs it to the terminal.

To log out of the remote server in your terminal, you can use:\ 
* Ctrl + D
* Run the command `exit`.
It should say logout and connection to ieng6.ucsd.edu closed.

An example of running such commands is: \
![Image2](commands.png)
