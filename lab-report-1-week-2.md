# Lab 1 Report - Week 2
* **Installing VSCode**
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-MJplNxD5h8RpBg9kKz-33Qd6O7UrHPny-yFRyyPUlYZtBZCUKeFyCUPmIA-PRv2OPABJhl6BiUBrj47p7HmJw9jXMoZaMFIZl51Eg=s1600)
I installed Visal Studio Code by downloading it from Visual Studio's website and running it. This image depicts the welcome page of VSCode.
* **Remotely Connecting**
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-MWYqYovRpvJ4dgy5D-_whPTYjuTjnJs-37YnV8O33_XpTFlVWSyHGRD7rUiEjgf0ExKuUVbFpkIs1KGliGf-XUHes_s1fVT2upPzM=s1528)
I then installed a program called Open SSH, which allows me to connect to other computers. I used VSCode's remote option to connect to a server by typing "ssh (my account here)." I answered "yes" to the connection confirmation question and entered my password.
* **Trying Some Commands**
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-PhaA_dtz8jMRX7f84eANgaGX7vm_7w4ai1709CeGn0xgFMxAcu42anwcIEZW0POgew6JTAoYPTyg-Y8VOMOcFGF1MxVynyQXd5vwE=s1600)
Running commands on the client
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-OWKk8WY9UjhXc0Z4bv6adE4rFzuwgm9qRVXuPxA9g77C1FnutuxyWJZ2Qf8c14-u-OVhVVdFFDHnMC6vkIbw8zT4GC3Ix06EADAK0=s1574)
Running commands on the server
Some commands do not work when run on the client, but work when run on the server. This is due to the fact that these commands involve directories that are only on the server.
* **Moving Files with scp**
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-OWLEuBWXCCRnJAxLE7qYzjLXmWw1f6d6lHaG8jZ0HglgU-AHSw8V3m_t6rKqqEUIc1ZNT0dVxYP5BtMv8Z-Fl_3wtydXNsJ98luaY=s1600)
I moved the file "labOne.java" to the remote server. I used the OPENSSH directory and .\scp instead of scp because currently my PATH cannot reach the scp and ssh commands.
* **Setting an SSH Key**
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-PQxeWErnsluY_SFfz3JjSgIBBAXLbSFMqy8gWZED058hnHYq_kDOvzGHyDjPJak1EQfymY7W6Q31pVGZuOLMEhqLRNk00Sgeone6Q=s1376)
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-N3BdJ7ZPwD8xU5wEjWCTPoUYoIsFiXZMX4ZHjxMliWNOs4l8xLCb7v0idvPyBO81Xcopayf9vKKBCp0QkuKd95P5I-mhf8OXgqCLU=s1600)
This step is meant to allow me to connect and copy files to the server without entering the password I set up previously. The commands can use the two files created instead of that password.
* **Optimizing Remote Running**
![Image](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-OQ5HAcViwobAwItvExjZET7th2eSStUZDnGbuC99fI5eMFJvbx5r_EeW0jNSBdc9mM5R8IxqepfXZwoJEazbUdNN6ompho1E5pCms=s1100)
This command lists the files in the home directory of the server. For copying local edits to the remote server, it is convenient to connect to the server and run all the necessary commands in one line. I can do this by placing quotation marks around all the files and semicolons in between each, ensuring that they are all separately copied to the server.