# Descargar y ejecutar un script utilizando SendKeys
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2016/01/28/descargar-y-ejecutar-un-script-utilizando-sendkeys/
```PowerShell
#Abrir PowerShell
[System.Windows.Forms.SendKeys]::SendWait("^({ESC})")
[System.Windows.Forms.SendKeys]::SendWait("EJECUTAR")
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")
Start-Sleep -Seconds 2
[System.Windows.Forms.SendKeys]::SendWait("powershell Start-BitsTransfer -Source 'https://www.jesusninoc.com/wp-content/uploads/2014/12/config.txt' -Destination $env:TEMP\config.ps1;")
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait("^({ESC})")
[System.Windows.Forms.SendKeys]::SendWait("EJECUTAR")
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")
Start-Sleep -Seconds 5
[System.Windows.Forms.SendKeys]::SendWait("powershell -File $env:TEMP\config.ps1")
[System.Windows.Forms.SendKeys]::SendWait("{ENTER}")

```
