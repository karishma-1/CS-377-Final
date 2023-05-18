Earlier in the semester, Project 2 was the Simple Shell project, where the goal was to implement a simple shell in C++. I utilized concepts such as pip, fork, exec, and waitpid to complete the given functions, which were parse_command(), exec_command(), and is_Quit(), and successfully completed the project. I really enjoyed the project, and wanted to add more functionality and extend it for my final project. 

For my final project, I will be using the skeletal code from Project 2 and extending it to include piping commands. I created a function called piping_commands() and modified the exec_command() function to fit the new functionality of piping_commands(). In addition, I modified the main file and tsh.h files.

Modifications I made: 
    tsh.h -- I added the piping_commands() and exec_piping_command() functions to the header file (tsh.h). 

    main_tsh.cpp -- The biggest changes I made was adding a boolean character called findPipeChar that finds the pipe “|” character in the cmd’s character array, if it exists. I also modified the while loop to include the two functions I created, if the pipe character is found. 

    tsh.cpp -- 
        My code for piping_commands() in the tsh.cpp file. It takes in an argument, and cmd and cmdTokens since they get passed through parse_command(). This is the external function that calls exec_piping_command(), which is the meat of the whole program. 
        
        exec_piping_command() is a new function I wrote specifically for piping_commands() and serves as the basis for executing pipes. I used the existing system call pipes() and used the file descriptor passed as an argument and forked it to create 2 child processes. An error message should be outputted if fork failed to execute. On success, fork again to get 2 new child processes and then check for an error. Upon success again, duplicate the file descriptor in filedes to STDOUT_FILENO or STDIN_FILENO and close the file descriptor. 


https://drive.google.com/file/d/1FBbvQzH9gWNTpmteGGv9-4xAj0ELhFHk/view 
Above is the link to my video and presentation. 