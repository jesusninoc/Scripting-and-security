# Mostrar fecha y hora en IE con JavaScript desde PowerShell
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/16/mostrar-fecha-y-hora-en-ie-con-javascript-desde-powershell/
```PowerShell
$ie = New-Object -com "InternetExplorer.Application"
$ie.Navigate("about:blank")
$ie.visible = $true

$ie.document.write("<script>alert(Date()) </script>") 
$doc = $ie.Document

```
