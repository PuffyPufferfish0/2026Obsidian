# `make` and Makefiles

`make` is a build automation tool that automatically builds executable programs and libraries from source code by reading files called `Makefiles`. It is heavily used in C and C++ development.

### The Makefile Structure

A Makefile consists of a set of rules. Each rule typically has three parts:

1. **Target**: The name of the file being generated (or a specific action name like `clean`).
    
2. **Dependencies**: The files required to build the target.
    
3. **Actions**: The shell commands to execute (these **must** be indented with a `Tab`, not spaces).
    

### Example Makefile

```
build: main.cpp
	g++ -o my_app main.cpp

run: my_app
	./my_app

clean:
	rm my_app
```

### Usage

- **`make build`**: Executes the instructions under the `build` target to compile the code.
    
- **`make run`**: Executes the compiled application.
    
- **`make clean`**: Removes the compiled executables to clean up the directory.
    
- **`make`**: If no target is specified, it runs the first target in the file by default.