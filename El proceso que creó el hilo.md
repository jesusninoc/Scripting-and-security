# El proceso que creó el hilo
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/04/12/el-proceso-que-creo-el-hilo/
```PowerShell
(Get-WmiObject -Class Win32_Thread).ProcessHandle | %{
Get-Process -Id $_
}

```
```PowerShell
(Get-WmiObject -Class Win32_Thread).ProcessHandle | %{Get-Process -Id $_} | Group-Object

```
