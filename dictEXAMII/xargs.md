# `xargs`

`xargs` is an advanced pipeline tool. While standard piping (`|`) takes the _output_ of one command and passes it as the _standard input_ of the next, `xargs` takes standard input and converts it into **arguments** for another command.

example

```
ls /var/log/*.log | xargs grep "ERROR" | wc -l
```

**Why use xargs here?**

1. `ls /var/log/*.log` outputs a list of filenames.
    
2. If we just piped that to `grep`, grep would search the literal _text_ of the filenames for "ERROR".
    
3. By inserting `xargs`, it takes those filenames and puts them at the end of the grep command, like this: `grep "ERROR" file1.log file2.log file3.log`.
    
4. Finally, `wc -l` counts the total number of lines where "ERROR" was found across all those files.