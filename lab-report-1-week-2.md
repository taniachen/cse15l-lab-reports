# Lab 1 Report - Week 2
* **Installing VSCode**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img1.png)
I installed Visal Studio Code by downloading it from Visual Studio's website and running it. This image depicts the welcome page of VSCode.

    [Download VSCode](https://code.visualstudio.com/)

* **Remotely Connecting**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img2.png)
I installed a program called Open SSH, which allows me to connect to other computers. Then, I looked up my CSE15L course-specific account [here](https://sdacs.ucsd.edu/~icc/index.php).
I used VSCode's remote option to connect to a server by typing   ```$ ssh cs15lwi22zz@ieng6.ucsd.edu```
into the terminal. I answered "yes" to the connection confirmation question and entered my password.

* **Trying Some Commands**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img3.png)
Running commands on the client
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img4.png)
Running commands on the server
Some commands do not work when run on the client, but work when run on the server. This is due to the fact that these commands involve directories that are only on the server.

    Commands ```cd``` and ```cd ~``` work on the client, while ```ls -lat```, ```ls -a```, ```cp /home/linux/ieng6/cs15lwi22/public/hello.txt ~/```, and ```cat /home/linux/ieng6/cs15lwi22/public/hello.txt``` work exclusively on the server.

* **Moving Files over SSH with scp**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img5.png)
I created a java file called WhereAmI.java, and placed this code inside it.
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
    I moved the file "WhereAmI.java" to the remote server using the command ```.\scp WhereAmI.java cs15lwi22afx@ieng6.ucsd.edu:~/```. I used the OPENSSH directory and .\scp instead of scp because currently my PATH system variable cannot reach the scp and ssh commands (this issue has since been fixed).
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/lab1img.png)
Running the file on the *ieng6 computer*.

* **Setting an SSH Key**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img10.png)
I used ```ssh-keygen -t ed25519``` to create a public and private key on my computer using the Ed25519 algorithm.
I then connected remotely (using ```ssh cs15lwi22afx@ieng6.ucsd.edu``` and the passphrase established earlier) and created a new directory in my user account on the server by entering ```mkdir .ssh```.
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img11.png)
I then copied the public key to the new directory using
```scp /Users/thebl/.ssh/id_rsa.pub cs15lwi22afx@ieng6.ucsd.edu:~/.ssh/authorized_keys```, allowing me to ssh and scp from my client to the server without entering my password.

* **Optimizing Remote Running**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img12.png)
The first command connects to the server and lists all the files in the home directory, while the second shows that multiple commands can be run when using a semicolon.
For copying local edits to and running commands on the remote server, it is most time-savvy to copy and connect to the server and run the commands all in one line. I can do this by copying to the server, connecting to the server, and placing quotation marks around all the commands and semicolons in between each.
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img13.png)
```scp WhereAmI.java cs15lwi22afx@ieng6.ucsd.edu:~/; ssh cs15lwi22afx@ieng6.ucsd.edu "javac WhereAmI.java; java WhereAmI"```

    This command takes 87 characters, and my passphrase takes 24 more. Total, there are 111 characters typed (114 including the three enters) and 1 click made. This all takes approximately 20 seconds. However, because this is all on one line, if I want to make a local edit to WhereAmI.java, copy it to the remote server, and run it (again), all I have to do is press the up arrow on my keyboard, press enter, and enter in my passphrase twice. This all takes approximately 7 seconds. Assuming that I will be making many edits to a file and running that file frequently, this is an efficient command.  