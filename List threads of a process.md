# List threads of a process
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2012/04/23/list-threads-of-a-process/
```PowerShell
$name = ‘notepad’
$count=0
foreach($procesoid in (Get-Process -Name $name).Id){
$count+=((Get-WmiObject -Class Win32_Thread).where{$_.ProcessHandle -match $procesoid}).count
Write-Host ‘PID:’ $procesoid ‘process’ $name ‘threads:’ $count
$count=0
}

```
