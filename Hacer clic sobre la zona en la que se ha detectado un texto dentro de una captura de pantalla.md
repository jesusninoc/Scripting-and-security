# Hacer clic sobre la zona en la que se ha detectado un texto dentro de una captura de pantalla
## Automation, Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/06/hacer-clic-sobre-la-zona-en-la-que-se-ha-detectado-un-texto-dentro-de-una-captura-de-pantalla/
```PowerShell
#Abrir por ejemplo google.es y realizar una búsqueda

[Reflection.Assembly]::LoadWithPartialName("System.Drawing")
function screenshot([Drawing.Rectangle]$bounds, $path)
{
$bmp = New-Object Drawing.Bitmap $bounds.width, $bounds.height
$graphics = [Drawing.Graphics]::FromImage($bmp)
$graphics.CopyFromScreen($bounds.Location, [Drawing.Point]::Empty, $bounds.size)
$bmp.Save($path)
$graphics.Dispose()
$bmp.Dispose()
}
#Cadena a buscar dentro de la captura

$cadena='jesusninoc'

for($i=220; $i -ne 720; $i+=100)
{
$i
$bounds = [Drawing.Rectangle]::FromLTRB(120, $i, 680, $i+100)
$fichero='F:\power\captura'+$i+'.png'
screenshot $bounds $fichero
cd 'C:\Program Files (x86)\Tesseract-OCR'
$ficheroout='F:\power\captura'+$i
.\tesseract.exe $fichero $ficheroout -l spa

$ficherocontxt=$ficheroout+'.txt'
$contenido=Get-Content $ficherocontxt -Encoding UTF8
$contenido
if($contenido -match $cadena)
{
$i+20 | Out-File f:\power\posiciones.txt -Append
}
}
$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@

$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru
#Pulsar en resultados positivos

Get-Content F:\power\posiciones.txt | %{
Start-Sleep -Seconds 2
$param1=155
$param2=$_
$param1
$param2
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point($param1,$param2)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
}

```
