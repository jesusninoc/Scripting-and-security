# Ver la configuración del Escritorio remoto
## PowerShell, Registry 
### URL: https://www.jesusninoc.com/2016/05/09/ver-la-configuracion-del-escritorio-remoto/
```PowerShell
cd HKLM:\
$RegKey ='HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Terminal Server\'
Get-ItemProperty -Path $RegKey -Name fDenyTSConnections

```
