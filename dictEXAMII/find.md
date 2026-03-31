# `find`

The `find` command is a powerful utility for searching files and directories across the entire filesystem based on highly specific criteria (name, size, permissions, date modified).

### Exam 2 Bonus Example

```
sudo find / -name "*.tmp" -delete
```

**Breakdown:**

- `sudo`: Runs as root (necessary to search the whole filesystem without permission denied errors).
    
- `find`: The command.
    
- `/`: The starting directory (in this case, the absolute root of the system, so it searches _everything_).
    
- `-name "*.tmp"`: The search parameter. Looks for any file ending in `.tmp`.
    
- `-delete`: The action. Automatically deletes any files that match the criteria.