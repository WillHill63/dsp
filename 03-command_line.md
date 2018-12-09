# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> > **Cheat Sheet of Unix Commands** .    

**pwd** --> show current working directory path.   

**mkdir** --> create a directory.  

**rm -R** --> delete a directory and the files within the directory.    

**touch filename** --> create a new file.   

**rm filename** --> delete a file.   

**mv filename1 filename2** --> rename file1 as file2.   

**ls -ld .** --> lists only the hidden files on a directory.   

**cp filename /destination_directory** --> copy a file from current directory to another directory.      

**cat filename** --> displays the contents of a file to the screen.    

**grep text filename** --> search a file for the specified text and displays the results on the screen.    
 

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

> > **Commonly Used Unix Commands** . 

**ls** --> lists files and subdirectories on a given directory.   

**ls -a** --> lists *all* files and subdirectories (including hidden ones) on a given directory.   

**ls -l** --> lists files and subdirectories in long format.    

**ls -lh** --> lists files and subdirectoris in long format, with filesizes expressed in human readable format (B, K or M).   

**ls -lah** -->  lists all files and subdirectories (including hidden ones) in long format and with the filesizes expressed in human readable format (B, K, or M).    

**ls -t** --> lists files and subdirectories on a directory, showing the newest ones first.    

**ls -Glp** --> lists files and subdirectories in long format, with subdirectories appended bu '/'.  The output is color coded. Subdirectory names are printed in blue, and files are printed in either red or green.      

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > **Five Other Versions of the 'ls' Command:**.   
    
**ls -m** --> displays files and subdirectories on a directory as a comma separated list.    

**ls -p** --> displays files and subdirectories on a directory, with the subdirectories appended by '/'.    

**ls -r** --> displays files and subdirectories on a directory in reverse order.     

**ls -R** --> displays files and subdirectories on a directory, as well as the files in each subdirectory.     

**ls -1** --> displays each file and subdirectory in the directory on a separate line.   


---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > **xargs** is a Unix command that builds an execution pipeline from standard input.  For example, the command  

    "echo 'metis_work, python_files, excel_worksheets, word_documents, seaborn_graphs' | xargs mkdir"  

would read the standard input string, split out the five items separated by a space and create directories named after each item in the input string.  Running the command would create five new directories named 'metis_work', 'python_files', 'excel_worksheets', 'word_documents' and 'seaborn_graphs'.  


 

