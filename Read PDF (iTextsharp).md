# Read PDF (iTextsharp)
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/09/25/read-pdf-itextsharp/
```PowerShell
#Download https://sourceforge.net/projects/itextsharp/
#Set paths: iTextSharp, PDF
$iTextSharpFilePath = "C:\Users\user1\Downloads\PowerShell.PDF\itextsharp.dll"
$pdfFilePath = "C:\Users\user1\Downloads\PowerShell.PDF\"

#Load iTextSharp
[System.Reflection.Assembly]::LoadFrom($iTextSharpFilePath)

#PDF example
$reader = New-Object iTextSharp.text.pdf.pdfreader -ArgumentList "$pdfFilePath\example.pdf"

for ($page = 1; $page -le $reader.NumberOfPages; $page++)
{
$lines = [char[]]$reader.GetPageContent($page) -join "" -split "`n"
foreach ($line in $lines)
{
if ($line -match "^\[")
{
$line = $line -replace "\\([\S])", $matches[1]
$line = $line -replace "^\[\(|\)\]TJ$", "" -split "\)\-?\d+\.?\d*\(" -join ""
$line
}
else
{
$line
}
}
}

```
