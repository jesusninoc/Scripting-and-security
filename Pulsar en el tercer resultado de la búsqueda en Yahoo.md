# Pulsar en el tercer resultado de la búsqueda en Yahoo
## PowerShell 
### URL: https://www.jesusninoc.com/2016/03/27/pulsar-en-el-tercer-resultado-de-la-busqueda-en-yahoo/
```PowerShell
#Para la resolución de pantalla 1366 x 768

#Importante:
#Sustituir las comillas ("") en línea DllImport

$MouseEventSig=@’
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
‘@

$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name 'MouseEventWinApi' -passThru

Start-Process Chrome 'https://es.search.yahoo.com/'

Start-Sleep -Seconds 5

[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(502,222)

[System.Windows.Forms.SendKeys]::SendWait('PowerShell')
[System.Windows.Forms.SendKeys]::SendWait('{ENTER}')

Start-Sleep -Seconds 5

#Pulsar en el primer resultado de la búsqueda

[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(252,377)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

```
