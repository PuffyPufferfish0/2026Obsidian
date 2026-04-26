A compiler is a specialized program that translates human-readable source code (written in high-level languages like C or C++) into machine-executable binary code that the computer's CPU can understand and run.

### Common Compilers

- **`gcc`**: The GNU Compiler Collection, standard for compiling **C** programs.
    
- **`g++`**: The standard compiler for **C++** programs.
    
- **`javac`**: The compiler for **Java** (translates source code to bytecode for the JVM).
    

### The Compilation Process (C/C++)

1. **Pre-processor**: Handles directives like `#include` and macros before actual compilation begins.
    
2. **Compiler**: Translates the pre-processed code into assembly language.
    
3. **Assembler**: Translates the assembly code into object code (binary).
    
4. **Linker**: Combines the object code with any necessary libraries to create the final executable file (like an `.exe` on Windows or an ELF on Linux).
    

### Basic Usage

- **Syntax**: `g++ -o [output_executable_name] [source_file.cpp]`
    
- **Example**: `g++ -o todo_app main.cpp` (Compiles `main.cpp` into an executable named `todo_app`).