# Prioridad de los hilos de los procesos
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/08/03/prioridad-de-los-hilos-de-los-procesos/
```PowerShell
(Get-WmiObject -Class Win32_Thread) | Select-Object ProcessHandle,Priority,PriorityBase | Sort-Object ProcessHandle

```
```PowerShell
(Get-Process).Threads | Select-Object Id,CurrentPriority,BasePriority | Sort-Object Id

```
