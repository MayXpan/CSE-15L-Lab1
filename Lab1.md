# Using cd, ls and cat in different situations
## When using the three different commands with no arguments

   1. ![image](<Lab1 cd1.png>)
   - In the image above, it can be seen that the current working directory is the home directory as there is nothing after the tilde.  The function of the 'cd' command is to change the working directory so by not stating a directory in the argument of the command nothing happens.  As such it is not an error.

   2. ![Image](<Lab1 ls1.png>)
   - Like the previous image, the current working directory is the home directory.  When using the ls command it lists what is contained in the current working directory, which in this case is lecture1.  There is no error

   3. ![Image](<Lab1 cat1.png>)
   - Again, currently in the home directory.  The functions of the cat command is to create, merge, or print file(s).  As such, by not putting any argument after it and leaving it blank, nothing happens and it reads from standard input.  As such there is no error.

## When using commands with directory as argument

   1. ![Image](<Lab1 cd2.png>)
   - The working directory before inputting an argument is the home directory, but after inputting the command with a directory, which in this case is lecture1, it changes the working directory to the one specified in the argument.  There is no output, but in the next line after entering the command, it can be seen that after the tilde it now says '/lecture1' indicating that the working directory has now changed to lecture1 from the home directory, so there is no error.

   2. ![Image](<Lab1 ls2.png>)
   - The working directory is the home directory.  When the argument is a directory when using the command 'ls' it prints out all the files and directories that are contained in the argument, which in this case is Hello.class, Hello.java, messages (another directory), and README.  There are no errors

   3. ![Image](<Lab1 cat2.png>)
   - The working directory is the home directory.  When the argument is a directory when using the command 'cat' it returns a message saying that lecture1 is a directory.  Because lecture1 is not a file, it is unable to print out what is contained in it.  The output is indicating that there was an error and that the argument was not compatible with the command.

## When using commands with a file as argument

   1. ![Image](<Lab1 cd3.png>)
   - The working directory is lecture1. The cd command can only have directories as arguments because it's purpose of changing the working directory, therefore a file as the argument will not work.  As such, it returns an error message saying that the argument is not a directory.

   2. ![Image](<Lab1 ls3.png>)
   - The working directory is lecture1. The ls command simply prints what files and/or directories are in the argument, and because the argument is a file itself it just prints the file that is inputted as the argument, which in this case is Hello.java. There is no error.

   3. ![Image](<Lab1 cat3.png>)
   - The working directory is lecture1. The cat command when the argument is a file prints out the contents of the specified file, which in this case is the code that is contained in the Hello.java file. The output is not an error.
