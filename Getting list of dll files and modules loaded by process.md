# Getting list of dll files and modules loaded by process
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2014/02/25/getting-list-of-dll-files-and-modules-loaded-by-process/
```PowerShell
#Example: notepad
#Select
get-process notepad | select -expand modules
#Or ().
(get-process notepad).Modules

```
