# Obtener el color de un pixel
## Automation, Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/10/25/obtener-el-color-de-un-pixel/
```PowerShell
$GDI = Add-Type -MemberDefinition @'
[DllImport("user32.dll")]
static extern IntPtr GetDC(IntPtr hwnd);

[DllImport("user32.dll")]
static extern Int32 ReleaseDC(IntPtr hwnd, IntPtr hdc);

[DllImport("gdi32.dll")]
static extern uint GetPixel(IntPtr hdc,int nXPos,int nYPos);

static public int GetPixelColor(int x, int y)
{
IntPtr hdc = GetDC(IntPtr.Zero);
uint pixel = GetPixel(hdc, x, y);
ReleaseDC(IntPtr.Zero,hdc);

return (int)pixel;
}
'@ -Name GDI -PassThru

for ()
{
Start-Sleep -m 1000
$dX = ([System.Windows.Forms.Cursor]::Position.X) #X coordinates
$dY = ([System.Windows.Forms.Cursor]::Position.Y) #Y coordinates
Write-Host $dX,$dY #print coordinates

$PixelColorRef = $GDI::GetPixelColor($dX,$dY)
$PixelColorRef
[System.Drawing.Color]::FromArgb($PixelColorRef)
}

```
