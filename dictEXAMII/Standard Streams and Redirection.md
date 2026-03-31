Every process in Linux automatically has 3 standard streams connected to it. These dictate where data comes from and where output goes.
## The 3 Standard Streams

1. **Standard Input (`stdin`)**:
    
    - File Descriptor: `0`
        
    - Purpose: Where data is fed into the program (default: the keyboard).
        
2. **Standard Output (`stdout`)**:
    
    - File Descriptor: `1`
        
    - Purpose: Where successful output is sent (default: the terminal screen).
        
3. **Standard Error (`stderr`)**:
    
    - File Descriptor: `2`
        
    - Purpose: Where error messages are sent (default: the terminal screen).
        

## Redirection Operators

You can change where these streams point using redirection operators:

- `>` : Redirects standard output to a file, **overwriting** the file. (e.g., `echo "hi" > file.txt`)
    
- `>>` : Redirects standard output, **appending** to the file. (e.g., `echo "hi" >> file.txt`)
    
- `2>` : Redirects standard error only. (e.g., `find / -name "*.txt" 2> errors.log`)
    
- `&>` : Redirects _both_ stdout and stderr to the same file simultaneously.
    
- `<` : Redirects standard input from a file instead of the keyboard.
    

## Piping (`|`)

Piping connects the output of one command directly to the input of another.

- Takes the `stdout` of the command on the left and passes it as `stdin` to the command on the right.
    
- _Example:_ `ls -la /var/log | grep "Feb" | wc -l` (Lists files, finds ones from February, counts how many there are).
    

## Exit Codes (`$?`)

Every command leaves behind an exit status code when it finishes.

- Check the exit code of the _very last run command_ using: `echo $?`
    
- **`0`** = Success (The command completed without errors).
    
- **`>0`** (Non-zero) = Failure/Error (Something went wrong).