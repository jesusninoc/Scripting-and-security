# Activar y mover un proceso de una posición de la pantalla a otra
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/02/20/activar-y-mover-un-proceso-de-una-posicion-de-la-pantalla-a-otra/
```PowerShell
#Abrir Notepad en una posición y después indicarle otra en la función MoveWindow

Add-Type @"
using System;
using System.Runtime.InteropServices;
public class Win32 {
[DllImport("user32.dll")]
public static extern bool MoveWindow(IntPtr hWnd, int X, int Y, int nWidth, int nHeight, bool bRepaint);
}
"@

$Script=New-Object -ComObject WScript.Shell
$Proceso=Get-Process notepad
#$Proceso=Get-Process mspaint
$Script.AppActivate($Proceso.MainWindowTitle)
[Win32]::MoveWindow(($Proceso).MainWindowHandle, 100, 200, 300, 400, $true)

```
