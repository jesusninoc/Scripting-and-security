# Priority of thread
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/07/26/priority-of-thread/
```PowerShell
(Get-WmiObject -Class Win32_Thread) | Select-Object ProcessHandle,Priority,PriorityBase | Sort-Object ProcessHandle

```
```PowerShell
(Get-Process).Threads | Select-Object Id,CurrentPriority,BasePriority | Sort-Object Id

```
