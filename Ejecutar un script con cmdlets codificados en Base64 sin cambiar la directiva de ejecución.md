# Ejecutar un script con cmdlets codificados en Base64 sin cambiar la directiva de ejecución
## Ducky scripts, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/25/ejecutar-un-script-con-cmdlets-codificados-en-base64-sin-cambiar-la-directiva-de-ejecucion/
```PowerShell
DELAY 750
GUI r
DELAY 750
STRING powershell Start-Process powershell_ise -Verb runAs
ENTER
DELAY 2050
ALT s
DELAY 2050
ENTER
CTRL R
ENTER
CTRL I
STRING Start-Process -FilePath powershell.exe -ArgumentList '-encodedcommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA=='
ENTER
DELAY 2050
F5

```
