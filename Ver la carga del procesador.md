# Ver la carga del procesador
## Hardware, PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/11/26/ver-la-carga-del-procesador/
```PowerShell
Get-WmiObject win32_processor | Select-Object LoadPercentage

```
