# Día de instalación de Windows
## PowerShell 
### URL: https://www.jesusninoc.com/2014/04/01/dia-de-instalacion-de-windows/
```PowerShell
([WMI]'').ConvertToDateTime((Get-WmiObject Win32_OperatingSystem).InstallDate)

```
