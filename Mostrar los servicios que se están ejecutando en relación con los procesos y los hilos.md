# Mostrar los servicios que se están ejecutando en relación con los procesos y los hilos
## PowerShell, Processes, Services, Threads 
### URL: https://www.jesusninoc.com/2015/10/30/mostrar-los-servicios-que-se-estan-ejecutando-en-relacion-con-los-hilos-y-los-procesos/
```PowerShell
(Get-WmiObject -Class Win32_Service | Where-Object State -EQ ‘Running’) | %{
Write-Host $_.Name,$_.ProcessId,$_.State,(Get-Process -Id $_.ProcessId).Name,(Get-WmiObject -Class Win32_Thread | Where-Object ProcessHandle -EQ $_.ProcessId)
}

```
