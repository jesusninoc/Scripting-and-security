# Pulsar en el primer resultado de la búsqueda en Yahoo
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2015/12/27/pulsar-en-el-primer-resultado-de-la-busqueda-en-yahoo/
```PowerShell
#Para la resolución de pantalla 1366 x 768

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

[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(200,160)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)

```
