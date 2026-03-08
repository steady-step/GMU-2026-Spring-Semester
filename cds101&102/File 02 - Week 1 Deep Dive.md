# Week 1 Deep Dive

## The difference between R and Matlab
     R :  Made by statisticians. Specialized in turning raw data into insightful visualization.
     Matlab: Made by engineer. Specialized in calculating matrix and making a simulation based on scientific knowledge.
     
## Deep Dive about R environment
     r : interpreter for executing r file. r needs interpreter because r is not compile language. 
     r studio : A program for making .r file
     git : this can record the process of your r file. You can recover your r file whenever you want. Also, you can compare this file to previous file.
     github: The online version of git. You can use token for using this.

 ## About the process for executing R

     r.exe(interpreter)
     package : it is just zip file. when we unzip this file, there are many .c files. 
     rtool.exe -> the file for making .c files to .dll
     lib(.dll)-> the dynamic library. r.exe always links these files when we use functions.

     First of all, you can download package file... and when we unzip this file, there are many .c files. We should understand the structure of c language. 
     When we make c programs, there are 4 processes. .c, .obj. .lib or .dll, .exe.... .c is just code files like .r... and .obj is file made by compiler.
     and .lib is static library. and .dll is dynamic library. For example, printf is not just simple. it is library. There are many processes for printing
     'A' on monitor. System call, Kernel Mode, Handshaking, GPU, and We should write all rgb bits on frame buffer. It is not simple. So we use library. 
     We just type printf for printing 'A'. So, Like this, For using R, we also need library. There are two libraries. static, and dynamic. and we use dynamic.
     rtool.exe makes many c files in package into .dll. And, when we make .r code in rstudio, there are just some gui icons on window. But it can not execute
     themselves. R executes that as a interpreter. and there are many fuctions. So, it links .dll files for executing this. 
     
