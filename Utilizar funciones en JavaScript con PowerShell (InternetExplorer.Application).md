# Utilizar funciones en JavaScript con PowerShell (InternetExplorer.Application)
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/29/utilizar-funciones-en-javascript-con-powershell/
```PowerShell
$ie = New-Object -com "InternetExplorer.Application"
$ie.Navigate("about:blank")
$ie.visible = $true
 
$ie.document.write('<p id="mostrar"></p>

<script>
function multiplicar(a, b) {
 return a * b;
}
document.getElementById("mostrar").innerHTML = multiplicar(4, 3);
</script>')

#Resultado de la primera multiplicación
$ie.document.getElementById("mostrar").innerHTML

#Segunda multiplicación
$ie.document.write('<script>document.getElementById("mostrar").innerHTML = multiplicar(4, 4);</script>')

#Resultado de la segunda multiplicación
$ie.document.getElementById("mostrar").innerHTML

```
