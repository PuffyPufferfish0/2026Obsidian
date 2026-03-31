# `getopts`

`getopts` is a built-in Bash tool used to parse short command-line options (flags) passed to a script.

### Lab 06 Use Case

In Lab 06, `getopts` was used to build the `dotinstall` script. It allowed the script to understand flags like `-s` (setup), `-r` (remove), or `-a` (append), and execute different blocks of code depending on which flag the user provided.

### Why it's useful

Instead of manually checking `$1`, `$2`, etc. (which can break if the user passes arguments in a different order), `getopts` provides a standardized, flexible way to handle flags.