# Mediante un evento de botón mostrar la fecha y hora
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2012/10/15/mediante-un-evento-de-boton-mostrar-la-fecha-y-hora/
```PowerShell
$ie = New-Object -com "InternetExplorer.Application"
$ie.Navigate("about:blank")
$ie.visible = $true

$ie.document.write("<button onclic=""getElementById('date').innerHTML=Date()"">¿Qué fecha y hora es?</button><p id=""date""></p>") 
$doc = $ie.Document

```
