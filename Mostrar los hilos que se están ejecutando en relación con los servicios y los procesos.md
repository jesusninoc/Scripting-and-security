# Mostrar los hilos que se están ejecutando en relación con los servicios y los procesos
## PowerShell, Processes, Services, Threads 
### URL: https://www.jesusninoc.com/2015/10/28/mostrar-los-hilos-que-se-estan-ejecutando-en-relacion-con-los-servicios-y-los-procesos/
```PowerShell
$i=0
(Get-WmiObject -Class Win32_Thread) | %{
$i++
Write-Host $i,$_.Handle,$_.ProcessHandle,(Get-WmiObject -Class Win32_Service | Where-Object State -EQ ‘Running’ | Where-Object ProcessId -EQ $_.ProcessHandle),(Get-Process -Id $_.ProcessHandle).ProcessName
}

```
