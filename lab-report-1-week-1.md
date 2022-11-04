# **TUTORIAL: HOW TO LOG INTO A COURSE-SPECIFIC ACCOUNT**
## In this tutorial, we will be using the `ieng6` server.
### This is also a walkthrough of what I have done in this week's lab.
--- 

**Step 1. Install Visual Studio Code**

**Note: This is an important step as having VSCode installed will make it easier for us to see what is going on as we write our webpage. In VSCode, we are able to see the outcome of whatever we are writing (left-hand side) on the right-hand size; like a split screen. We can identify any mistakes early on by having an image of what we are writing.**


To download VSCode, navigate to the [Official VSCode Website](https://code.visualstudio.com/). Follow the instructions for a successful download. Once downloaded, your screen should look like this once you launch the application: 


![vscodewelcome](https://user-images.githubusercontent.com/114317681/193370733-f3212edb-8ef7-4cd9-a5b0-dad23dc5c785.png)


**Step 2. Remotely Connecting to Another Server**

* First, [Install OpenSSH](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui). Your pc might already have the **OpenSSH Client**, but not the **OpenSSH Server** (which was what happened in my case). Make sure both are installed. 
* When those two are installed, follow the intructions on the website for the rest of the commands in order to ensure functionality. 
* Then, launch VSCode, and open up a new terminal. Type out `$ ssh cs15lfa22<>@ieng6.ucsd.edu`. You shouldn't write the `<>` in there, it is just a placeholder--you need to know what your CSE15L account is for this step.
![image](https://user-images.githubusercontent.com/114317681/195715324-3035097d-add9-4fdc-bde9-2ec73fb0012d.png)
(Note: [Your course-specific account can be found here](https://sdacs.ucsd.edu/~icc/index.php)). 
* Before connecting, you will get a message asking if you want to keep connecting. Type 'yes.'
* Once successfully connected, you will see the following in your terminal: 
![image](https://user-images.githubusercontent.com/114317681/195957563-06f210ff-3334-44ef-aea5-cf2000431ccb.png)

**Congratulations! You have successfully connected to a remote server! :)**

**Step 3. Trying out Commands**


In this part, we will be trying out some commands on our newly connected account. 
* Let's start using the `ls -lat` command: 
![lat](https://user-images.githubusercontent.com/114317681/193378307-47c7752c-0120-40af-bdee-2df10f34dfd0.png)
What this command will do is basically show a list of all directories, and existing files, sorted by when they were created. 
* For the next commaned, let's try `ls -a`, which will also show all files, without any timestamps or dates: 
![lsa](https://user-images.githubusercontent.com/114317681/193378808-5cdf958e-f46b-4422-b162-82de3728b536.png)
* Finally, running the `cat /home/linux/ieng6/cs15lfa22/public/hello.txt` command will print out the contents of the **hello.txt** file: 
![cat](https://user-images.githubusercontent.com/114317681/193378864-6aac4d81-ac3b-4c77-afa5-deb012ad8184.png)

    which is a small welcome to the course! 

**Now you know how to run commands on a remote server! :D** 

**Step 4. Moving Files with the `scp` Command** 

* Create a java file on on your computer called `WhereAmI.java`, with the following contents: 
```
class WhereAmI {
    public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

* Before compiling and running the file, type `exit` onto the terminal to exit the remote account. ![exit](https://user-images.githubusercontent.com/114317681/193379255-77e261b6-70a5-4e2c-9d74-b48b6d87deeb.png)

* Next, compile and run the file using the `javac` and `java` commands.
![whereamiwindows111](https://user-images.githubusercontent.com/114317681/193394054-4046ac41-5440-4197-a489-d9c87c36218b.png)
    - As you can see, running this file on my computer will only print out facts about my computer: the OS, which is Windows 11, and the user's name, which is my name, Viann, but it doesn't print out the rest of the information. 

* Now, let's run the `scp` command in order to copy the file, as shown below:
```
scp WhereAmI.java cs15lfa22zz@ieng6.ucsd.edu:~/
```
![copyscp](https://user-images.githubusercontent.com/114317681/193394516-0baf5622-a6db-4f33-b813-c4fd2a0fe696.png)

Note: The `scp` command stands for "Secure Copy Protocol," and it does just that: securely copies a file from one host to the other, remotely. 

* Upon completion, we run the `ssh` command, which will ensure a safe file transfer to our remote account: 
![ssh](https://user-images.githubusercontent.com/114317681/193394562-2bc84a92-b462-4ea3-859c-63342d37d19c.png)
    - As we can see, upon using the `ssh` command and we compile and run the `WhereAmI.java` file, we will get more information about our current remote account, as running these commands has printed out the OS, the name of the account, and even the directory of that account. 

**We just successfully copied a file from one computer to another remotely! :D**

**Step 5: Using an SSH key**

* For this part, we will be generating something that is called an `ssh` key. More specifically, the command is `ssh-keygen`. We will be using this very useful command in order to diminish the time it takes for us to completely log in remotely and when using `scp`, as we repeatedly have to be typing in our password everytime. 
* What `ssh-keygen` will do is fairly simple: it creates a pair of files, the "public key" and the "private key," and then the public key is copied to a particular location on the server, while the private key gets copied to a particular location on the client. After this, using the `ssh` command with this key already in place will allow us to use those files (the public and private keys) instead of our password. 
* In order to set this up, you should type the following command on your computer/terminal:

```
$ ssh-keygen
```

Which should bring up something like this afterwards: 

![image](https://user-images.githubusercontent.com/114317681/195959652-ce18a586-8281-4e3f-b455-cd34ca9d41d6.png)

* Following this, another message will pop up, which wil ask you for which file you want to save the key in. Just press enter, as we are specifying the default path, which should be something like this (/Users/your name/.ssh/id_rsa).
* It will then ask you for a "paraphrase." You can go ahead and type one in, but if you don't want any, then just press enter to leave it empty. 
* If successful, your terminal should look something like this: 

```
PS C:\Users\Viann\OneDrive\Documents\GitHub\cse15l-lab-reports> ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (C:\Users\Viann/.ssh/id_rsa): 
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in C:\Users\Viann/.ssh/id_rsa.
Your public key has been saved in C:\Users\Viann/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:YGLAwtiIYQWR6me7yce/Q4tLLR8HLUGkjO9gk1ieOsY viann@DESKTOP-LCQR4P1
The key's randomart image is:
+---[RSA 3072]----+
|=O*.  .o         |
|*oo.o o          |
|.. oooo.         |
|. +.+o .o        |
|.. B . oS.       |
|..oo+ ..o        |
| Eo o+oo..       |
|. o.o+ooo        |
|   +o.o+o        |
+----[SHA256]-----+
```

* This has created two files on our system: the private key, which is in the file `id_rsa`, and the public key, which is in the file `id_rsa.pub`, all stored in the `.ssh` directory on our computer. 
* Now, we need to copy the public key to the `.ssh` directory of our user account on the server. To do this, write out the following in your terminal: 

```
# on your client
$ ssh cs15lfa22<>@ieng6.ucsd.edu

(type out your password)
```

Note: the <> is a placeholder for the last two letters on your account. 

* Then, while being in the server, 

```
# now on the server

$ scp /Users/your name/.ssh/id_rsa.pub cs15lfa22@ieng6.ucsd.edu:~/.ssh/authorized_keys

(Note: use your username and the path you saw from the command above)
```
* Once you do this, you should be able to `ssh` or `scp` from this client to the server without entering your password. 

* Note: I will not be showing my screenshots for this part since I unfortunately couldn't get this to work for some reason, as I kept getting asked for my password when doing the `scp` part, and everytime I typed it out, it kept prompting me to keep inputing it. 

**Step 6: Attempting for Remote Running to be even More Pleasant**

* In this step, we will be attempting to come up with a stress-free process for making a local edit to the file we created previously, ``WhereAmI.java``, copying it to the remote server, and running it.
* Here are a few hints:
1) You are able to write a command in quotes at the end of an `ssh` command to directly run it on the remote server, and then exit. As an example, running this command will list the home directory on the remote server: 
```
$ ssh cs15fa22@ieng6.ucsd.edu "ls"
```
* Additionally, you are able to use semicolons to run multiple commands on the same line:

```
$ scp WhereAmI.java OtherMain.java; javac OtherMain.java; java WhereAmI
```
Please note: as mentioned previously, I was unable to get my `ssh` part working from the previous step, which also prevented me from completing this step. 

---

### With that, we have concluded this very short tutorial! Hopefully it was helpful as I walked you through what I did for my lab as well.

















