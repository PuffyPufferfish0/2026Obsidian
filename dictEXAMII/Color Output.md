# Color Output in Bash

You can make your scripts much more readable by using ANSI escape codes to output colored text to the terminal.

### How to use it

1. Define the color codes as variables in your script.
    
2. Use the `echo -e` command (`-e` enables interpretation of backslash escapes).
    
3. Use the `\033[0m` (No Color) code at the end to reset the terminal back to default text.
    

### Lab 07 `sys-info.sh` Example

```
# Define Colors
GREEN='\033[0;32m'
BLUE='\033[0;34m'
NC='\033[0m' # No Color

# Print with color
echo -e "${BLUE}=== SYSTEM SUMMARY ===${NC}"
echo -e "${GREEN}[OS/Kernel]${NC}"
```