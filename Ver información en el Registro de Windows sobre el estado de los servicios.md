# Ver información en el Registro de Windows sobre el estado de los servicios
## PowerShell, Processes, Registry, Services 
### URL: https://www.jesusninoc.com/2015/03/22/ver-informacion-en-el-registro-de-windows-sobre-el-estado-de-los-servicios/
```PowerShell
Get-ItemProperty -Path 'Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\*' | % {Write-host $_.DisplayName : $_.Start}

```
