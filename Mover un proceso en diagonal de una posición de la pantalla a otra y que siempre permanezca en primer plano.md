# Mover un proceso en diagonal de una posición de la pantalla a otra y que siempre permanezca en primer plano
## PowerShell 
### URL: https://www.jesusninoc.com/2016/04/11/mover-un-proceso-en-diagonal-de-una-posicion-de-la-pantalla-a-otra-y-que-siempre-permanezca-en-primer-plano/
```PowerShell
#Abrir Notepad
#¡Cuidado! porque puede desaparecer de la pantalla debido a la resolución de pantalla

Add-Type @"
using System;
using System.Runtime.InteropServices;
public class Win32 {
[DllImport("user32.dll")]
public static extern bool MoveWindow(IntPtr hWnd, int X, int Y, int nWidth, int nHeight, bool bRepaint);
}
"@

for($posicion=0;$posicion -lt 800;$posicion=$posicion+100)
{
$Script=New-Object -ComObject WScript.Shell
$Proceso=(Get-Process notepad)
$Script.AppActivate($Proceso.MainWindowTitle)
[Win32]::MoveWindow(($Proceso).MainWindowHandle, $posicion, $posicion, 500, 400, $true)
Start-Sleep -Seconds 2
}

```
