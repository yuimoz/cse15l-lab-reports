# **TUTORIAL: HOW TO LOG INTO A COURSE-SPECIFIC ACCOUNT**
## In this tutorial, we will be using the `ieng6` server.
### This is also a walkthrough of what I have done in this week's lab.
--- 

**Step 1. Install Visual Studio Code**

To download VSCode, navigate to the [Official VSCode Website](https://code.visualstudio.com/). Follow the instructions for a successful download. Once downloaded, your screen should look like this once you launch the application: 


![vscodewelcome](https://user-images.githubusercontent.com/114317681/193370733-f3212edb-8ef7-4cd9-a5b0-dad23dc5c785.png)


**Step 2. Remotely Connecting to Another Server**

* First, [Install OpenSSH](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse?tabs=gui). Your pc might already have the **OpenSSH Client**, but not the **OpenSSH Server** (which was what happened in my case). Make sure both are installed. 
* When those two are installed, follow the intructions on the website for the rest of the commands in order to ensure functionality. 
* Then, launch VSCode, and open up a new terminal. Type out `$ ssh cs15fa22<>@ieng6.ucsd.edu`. You shouldn't write the `<>` in there, it is just a placeholder--you need to know what your CSE15L account is for this step (Note: [Your course-specific account can be found here](https://sdacs.ucsd.edu/~icc/index.php)). 
* Before connecting, you will get a message asking if you want to keep connecting. Type 'yes.' (**NOTE**: Unfortunately, in my case, I was not able to remotely connect with my account, so I will be showing screenshots of remotely connecting with the TA's account instead).
* Once successfully connected, you will see the following in your terminal: 
![connected](https://user-images.githubusercontent.com/114317681/193378097-43708c5d-5b2f-4818-9e84-019c8b79a190.png)

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

**Step 4. Moving Files with the `scp` command** 

Note: this was done using the TA account, not mine, since I was not able to login. 

* Create a java file on on your computer called `WhereAmI.java`, with the following contents: 
![whereamiscreenshot](https://user-images.githubusercontent.com/114317681/193379109-50bd8803-e9f9-4944-8ec9-95f931ce49d6.png)

* Before compiling and running the file, type `exit` onto the terminal to exit the remote account. ![exit](https://user-images.githubusercontent.com/114317681/193379255-77e261b6-70a5-4e2c-9d74-b48b6d87deeb.png)

* Next, compile and run the file using the `javac` and `java` commands.
![whereamiwindows111](https://user-images.githubusercontent.com/114317681/193394054-4046ac41-5440-4197-a489-d9c87c36218b.png)
    - As you can see, running this file on my computer will only print out facts about my computer: the OS, which is Windows 11, and the user's name, which is my name, Viann, but it doesn't print out the rest of the information. 

* Now, let's run the `scp` command in order to copy the file:
![copyscp](https://user-images.githubusercontent.com/114317681/193394516-0baf5622-a6db-4f33-b813-c4fd2a0fe696.png)
* Upon completion, we run the `ssh` command, which will ensure a safe file transfer to our remote account: 
![ssh](https://user-images.githubusercontent.com/114317681/193394562-2bc84a92-b462-4ea3-859c-63342d37d19c.png)
    - As we can see, upon using the `ssh` command and we compile and run the `WhereAmI.java` file, we will get more information about our current remote account, as running these commands has printed out the OS, the name of the account, and even the directory of that account. 

**We just successfully copied a file from one computer to another remotely! :D**

**Step 5. Setting an SSH Key (INCOMPLETE)**
* Unfortunately, for this part, I was not able to complete it, as I ran out of time in the lab. Most of my time went into figuring out why I couldn't get access to my account remotely, and then I ended up using the TA account instead, but I ran out of time at that point and couldn't get to this step. 

---

### With that, we have concluded this very short tutorial! Hopefully it was helpful as I walked you through what I did for my lab as well. Until later! 

















