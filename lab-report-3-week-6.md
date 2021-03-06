# Lab 3 Report - Week 5
## Copying Directories With ```scp -r```

![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab3-ss1.png)
The command ```scp -r . cs15lwi22@ieng6.ucsd.edu:~/markdown-parse``` copies the current directory into a new directory called markdown-parse on the remote server. The `-r` tells `scp` to copy recursively, the `.` means the current directory, and the `~/markdown-parse` creates a new folder that `scp` copies into.

***

![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab3-ss2.png)
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab3-ss3.png)
Here, I `ssh` into my ieng6 account using the command `ssh cs15lwi22@ieng6.ucsd.edu` (this is not an account-specific command). Then, I compile and run MarkdownParseTest.java using the command `javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest`, which works for the Linux operating system.

***

![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab3-ss5.png)
![Image](https://raw.githubusercontent.com/taniachen/cse15l-lab-reports/main/images/lab3-ss6.png)
This command, ```scp -r . cs15lwi22@ieng6.ucsdedu: ~/markdown-parse7; ssh cs15lwi22@ieng6.ucsd.edu "cd markdown-parse 7; /software/CSE/oracle-java-se-14/jdk-14.0.2/bin/javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.1.3.2.jar MarkdownParseTest.java; /software/CSE/oracle-java-se-14/jdk-14.0.2/bin/java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.1.3.2.jar org.junit.runner.JUnitCore MarkdownParseTest```copies all the files in the current directory to a new folder called markdownparse-7 on the remote server. Then, it logs into an ieng6 account, and compiles and runs MarkdownParseTest.java. This command copies the entire directory and compiles and runs a file in one line.