# Insert image into a pdf (image to the appropriate dimension)
## PowerShell 
### URL: https://www.jesusninoc.com/2015/08/06/insert-image-into-a-pdf-image-to-the-appropriate-dimension/
```PowerShell
[System.Reflection.Assembly]::LoadFrom(“F:\power\PowerShell.PDF\itextsharp.dll”)
[System.Reflection.Assembly]::LoadWithPartialName("System.Drawing")

$document=New-Object itextsharp.text.document
$stream=[IO.File]::OpenWrite(“F:\power\output.pdf”)
[itextsharp.text.pdf.PdfWriter]::GetInstance($document, $stream)

$document.Open()

$bmp = New-Object System.Drawing.Bitmap('F:\power\captura.png')
$rect = New-Object iTextSharp.text.Rectangle($bmp.Width, $bmp.Height)
$document.SetPageSize($rect)
$document.NewPage()
$document.Add([iTextSharp.text.Image]::GetInstance('F:\power\captura.png'));
$bmp.Dispose()

$document.Close()
$stream.Close()

```
