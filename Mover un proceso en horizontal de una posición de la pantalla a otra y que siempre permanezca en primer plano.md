# Mover un proceso en horizontal de una posición de la pantalla a otra y que siempre permanezca en primer plano
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/02/28/mover-un-proceso-en-horizontal-de-una-posicion-de-la-pantalla-a-otra-y-que-siempre-permanezca-en-primer-plano/
```PowerShell
#Abrir Notepad

Add-Type @"
using System;
using System.Runtime.InteropServices;
public class Win32 {
[DllImport("user32.dll")]
public static extern bool MoveWindow(IntPtr hWnd, int X, int Y, int nWidth, int nHeight, bool bRepaint);
}
"@

for($posicion=100;$posicion -lt 800;$posicion=$posicion+100)
{
$Script=New-Object -ComObject WScript.Shell
$Proceso=(Get-Process notepad)
$Script.AppActivate($Proceso.MainWindowTitle)
[Win32]::MoveWindow(($Proceso).MainWindowHandle, $posicion, 200, 500, 400, $true)
Start-Sleep -Seconds 2
}

```
