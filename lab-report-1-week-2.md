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
I moved the file "WhereAmI.java" to the remote server using the command ```.\scp WhereAmI.java cs15lwi22afx@ieng6.ucsd.edu:~/```. I used the OPENSSH directory and .\scp instead of scp because currently my PATH system variable cannot reach the scp and ssh commands. (This has since been fixed.)
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/lab1img.png)
Running the file on the *ieng6 computer*.
* **Setting an SSH Key**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img6.png)
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img7.png)
This step is meant to allow me to connect and copy files to the server without entering the password I set up previously. The commands can use the two files created instead of that password.
* **Optimizing Remote Running**
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/img8.png)
This command lists the files in the home directory of the server. For copying local edits to the remote server, it is convenient to connect to the server and run all the necessary commands in one line. I can do this by placing quotation marks around all the files and semicolons in between each, ensuring that they are all separately copied to the server.
