A `.gitignore` file is a plain text file placed in the root of a Git repository that tells Git which files and directories to intentionally ignore and leave untracked.

### Purpose

It is used to prevent unwanted files from being committed to your repository. Common things to ignore include:

- Compiled binaries and executables (e.g., `.exe` or Linux executables).
    
- Temporary files and OS-generated files (e.g., `.DS_Store`).
    
- Log files or local environment variable files holding passwords/keys.
    

### Syntax & Examples

Inside the `.gitignore` file, you simply list the names or patterns of files to ignore:

- **`*.exe`**: Ignores all files ending in `.exe` (using the `*` wildcard).
    
- **`todo_app`**: Ignores the specific executable named `todo_app`.
    
- **`build/`**: Ignores the entire `build` directory.
    

### Removing Already Tracked Files

If a file was already tracked before you added it to `.gitignore`, you must manually remove it from Git's cache:

- **Command**: `git rm --cached [file_name]` (Removes it from Git tracking, but keeps the file safely on your hard drive).