# Ejecutar un script con cmdlets codificados en Base64 sin cambiar la directiva de ejecución (versión reducida)
## Ducky scripts, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/28/ejecutar-un-script-con-cmdlets-codificados-en-base64-sin-cambiar-la-directiva-de-ejecucion-version-reducida/
```PowerShell
DELAY 750
GUI r
DELAY 750
STRING powershell Start-Process -FilePath powershell.exe -ArgumentList '-encodedcommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA=='
ENTER
DELAY 2050

```
