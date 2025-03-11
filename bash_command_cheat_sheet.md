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

## File Inspection and Metrics

`wc <file name>` Prints the number of newlines, words, and bytes for the specified file.  
`wc -l <file name>` Prints the number of newlines for the specified file.
`grep "word" <file name>` Searches for the specified string/word in the specified file. Only lines containing the search string are output, with the matching portion of the line highlighted in red.  
`grep -P "pattern" <file name>` Searches for the specified regex pattern in the specified file using the Perl regex engine. Only lines containing a match are output, with the matching portion of the line highlighted in red.  
`grep -P -o "pattern" <file name>` Searches for the specified regex pattern in the specified file using the Perl regex engine. The `-o` option causes only the matching portions of each line to be output.

## File Compression and Integrity

`gzip <file name>` Compresses the specified file into gzip format.  
`gunzip <file name>` Decompress the specified gzipped file.  
`zcat <file name>` View a gzipped compressed file without decompressing it.  
`md5sum <file name>` Generate an md5sum for the specified file.  
`md5sum -c <md5sum files>` Read in a file containing md5sums and the file each sum is associated with, and verify that each file has the expected md5sum on your current system.  
`sum <file name` Calculate a checksum for the specified file. Similar to md5sum, but uses a different algorithm.
