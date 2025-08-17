Key Features:

Basic Shell Loop: Reads commands, parses them, and executes them in a continuous loop
Dynamic Memory Management: Handles input lines and argument arrays of arbitrary length
Built-in Commands:

cd - Change directory
help - Show available commands
exit - Exit the shell


External Program Execution: Can run any program in your system's PATH

How it Works:

Reading Input: Uses getchar() to read characters one by one, dynamically expanding the buffer as needed
Parsing: Splits the input line into tokens using whitespace as delimiters
Execution: Either runs built-in commands or forks a new process to execute external programs
Process Management: Uses fork() and execvp() to launch programs, with waitpid() to wait for completion

To Compile and Run:
bashgcc -o shell shell.c
./shell
Example Usage:
> ls -la
> cd /home/user
> help
> echo "Hello, World!"
> exit
Key System Calls Used:

fork() - Creates a child process
execvp() - Replaces the current process with a new program
waitpid() - Waits for child process to complete
chdir() - Changes the current directory