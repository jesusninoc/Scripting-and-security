# Ejercicios sobre procesos
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/10/12/ejercicios-sobre-procesos/
```PowerShell
#Listar todos los procesos
Get-Process
#Mostrar los 5 primeros procesos
Get-Process | Select-Object -First 5
#Mostrar los 5 últimos procesos
Get-Process | Select-Object -Last 5
#Ordenar todos los procesos por CPU de forma descendente
Get-Process | Sort-Object CPU -Descending

```
