# Listar los hilos de un proceso
## PowerShell, Processes, Threads 
### URL: https://www.jesusninoc.com/2015/07/22/listar-los-hilos-de-un-proceso/
```PowerShell
$name = ‘notepad’
$contador=0
foreach($procesoid in (Get-Process -Name $name).Id){
$contador+=((Get-WmiObject -Class Win32_Thread).where{$_.ProcessHandle -match $procesoid}).count
Write-Host 'PID:' $procesoid 'del proceso' $name 'tiene' $contador 'hilos'
$contador=0
}

```
