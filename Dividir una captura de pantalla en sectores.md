# Dividir una captura de pantalla en sectores
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/16/dividir-una-captura-de-pantalla-en-sectores/
```PowerShell
[Reflection.Assembly]::LoadWithPartialName("System.Drawing")
function screenshot([Drawing.Rectangle]$bounds, $path)
{
$bmp = New-Object Drawing.Bitmap $bounds.width, $bounds.height
$graphics = [Drawing.Graphics]::FromImage($bmp)
$graphics.CopyFromScreen($bounds.Location, [Drawing.Point]::Empty, $bounds.size)
$bmp.Save($path,'bmp')
$graphics.Dispose()
$bmp.Dispose()
}

#Parte izquierda: la posición x es igual a 0 hasta que la posición x sea igual a la mitad de la pantalla
for($i=0; $i -lt 720; $i=$i+30)
{
#Sin acumular, línea a línea de tamaño 30
$bounds = [Drawing.Rectangle]::FromLTRB(0, $i, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width/2, $i+30)
#Acumulado
#$bounds = [Drawing.Rectangle]::FromLTRB(0, 0 [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width/2, $i+30)
$fichero='d:\power\capturap\'+$i+'.png'
#Realizar captura
screenshot $bounds $fichero
D:\program\tesseract-ocr-3.02-win32-portable\Tesseract-OCR\tesseract.exe $fichero $fichero.Replace('.png','') -l eng | Out-Null
gc $fichero.Replace('.png','.txt')
}

#Parte derecha: la posición x es igual a la mitad de la pantalla hasta que la x sea igual al tamaño completo de la pantalla
for($i=0; $i -lt 720; $i=$i+30)
{
#Sin acumular, línea a línea de tamaño 30
$bounds = [Drawing.Rectangle]::FromLTRB([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width/2, $i, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, $i+30)
#Acumulado
#$bounds = [Drawing.Rectangle]::FromLTRB([System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width/2, 0, [System.Windows.Forms.Screen]::PrimaryScreen.Bounds.Width, $i+30)
$fichero='d:\power\capturap\'+$i+'.png'
#Realizar captura
screenshot $bounds $fichero
D:\program\tesseract-ocr-3.02-win32-portable\Tesseract-OCR\tesseract.exe $fichero $fichero.Replace('.png','') -l eng | Out-Null
gc $fichero.Replace('.png','.txt')
}

```
