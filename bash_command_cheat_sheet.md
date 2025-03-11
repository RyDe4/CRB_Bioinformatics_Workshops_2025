## Navigating Directories on the Command Line

`pwd` Gets the path of the directory you are currently in (your working directory).  
`cd <directory path>` Changes your current working directory to the specified directory.  
`ls` lists all the files and directories in your current working directory.  
`ls -l` lists all the files and directories in your current working directory with more information provided about each file.  
`ls <directory path>` lists all files in the specified directory.  

## Viewing Files

`head <file name>` Show the first 10 lines of the specified file.  
`head -20 <file name>` Show the first 20 lines of the specified file.  
`tail <file name>` Show the last 10 lines of the specified file.  
`cat <file name` Show all of the specified file.  
`cat <file name 1> <file name 2>` Show the specified files concatenated together.  
`less <file name>` Show the specified file in a scrollable view (use arrow keys to scroll up and down and q to exit).  

## File and Directory Management

`mkdir <directory name>` Create a directory with the specified name or path.  
`mv <file path/name 1> <file path/name 2>` Moves the file specified by the first argument to the location specified by the second argument. Can also be used to rename files.  
`mv -n <file path/name 1> <file path/name 2>` Moves the file specified by the first argument to the location specified by the second argument, only if there is not already a file with the same name at that location (prevents overwriting files).  
`cp <file path/name 1> <file path/name 2>` Copy the file specified by the first argument to the location specified by the second argument.
