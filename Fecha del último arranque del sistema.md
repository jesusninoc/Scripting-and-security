# Fecha del último arranque del sistema
## Forensic analysis, PowerShell 
### URL: https://www.jesusninoc.com/2016/06/24/fecha-del-ultimo-arranque-del-sistema/
```PowerShell
(Get-WmiObject -Class Win32_OperatingSystem).LastBootupTime

```
