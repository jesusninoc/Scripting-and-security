# List processes by memory
## Bash, Memory, Processes 
### URL: https://www.jesusninoc.com/2016/05/31/list-processes-by-memory/
```Shell
ps -e -orss=,args= | sort -b -k1,1n | pr -TW$COLUMNS

```
