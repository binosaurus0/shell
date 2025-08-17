## Key Features:

1. **Basic Shell Loop**: Reads commands, parses them, and executes them in a continuous loop
2. **Dynamic Memory Management**: Handles input lines and argument arrays of arbitrary length
3. **Built-in Commands**:
   - `cd` - Change directory
   - `help` - Show available commands
   - `exit` - Exit the shell
4. **External Program Execution**: Can run any program in your system's PATH

## How it Works:

1. **Reading Input**: Uses `getchar()` to read characters one by one, dynamically expanding the buffer as needed
2. **Parsing**: Splits the input line into tokens using whitespace as delimiters
3. **Execution**: Either runs built-in commands or forks a new process to execute external programs
4. **Process Management**: Uses `fork()` and `execvp()` to launch programs, with `waitpid()` to wait for completion

## To Compile and Run:

```bash
gcc -o shell shell.c
./shell
```

## Example Usage:

```
> ls -la
> cd /home/user
> help
> echo "Hello, World!"
> exit
```

## Key System Calls Used:

- `fork()` - Creates a child process
- `execvp()` - Replaces the current process with a new program
- `waitpid()` - Waits for child process to complete
- `chdir()` - Changes the current directory

This implementation is intentionally simple but demonstrates the core concepts of how shells work. It handles the fundamental operations of reading user input, parsing commands, and executing both built-in commands and external programs.

The shell will continue running until you type `exit` or send an EOF signal (Ctrl+D on most systems).