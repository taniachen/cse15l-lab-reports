# Lab 1 Report - Week 2
* **Installing VSCode**
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img1.png?raw=true)
I installed Visal Studio Code by downloading it from Visual Studio's website and running it. This image depicts the welcome page of VSCode.
* **Remotely Connecting**
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img2.png)
I then installed a program called Open SSH, which allows me to connect to other computers. I used VSCode's remote option to connect to a server by typing "ssh (my account here)." I answered "yes" to the connection confirmation question and entered my password.
* **Trying Some Commands**
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img3.png)
Running commands on the client
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img4.png)
Running commands on the server
Some commands do not work when run on the client, but work when run on the server. This is due to the fact that these commands involve directories that are only on the server.
* **Moving Files with scp**
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img5.png)
I moved the file "labOne.java" to the remote server. I used the OPENSSH directory and .\scp instead of scp because currently my PATH cannot reach the scp and ssh commands.
* **Setting an SSH Key**
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img6.png)
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img7.png)
This step is meant to allow me to connect and copy files to the server without entering the password I set up previously. The commands can use the two files created instead of that password.
* **Optimizing Remote Running**
![Image](https://github.com/taniachen/cse15l-lab-reports/blob/main/img8.png)
This command lists the files in the home directory of the server. For copying local edits to the remote server, it is convenient to connect to the server and run all the necessary commands in one line. I can do this by placing quotation marks around all the files and semicolons in between each, ensuring that they are all separately copied to the server.
