# Buscar varias palabras dentro de las descripciones de los resultados de una búsqueda en Google
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/21/buscar-varias-palabras-dentro-de-las-descripciones-de-los-resultados-de-una-busqueda-en-google/
```PowerShell
#Fichero con las palabras que hay que buscar dentro de las descripciones de los resultados de una búsqueda en Google
$ficheropalabras=gc D:\power\ficheropalabras.txt
$url='https://www.google.es/search?q=powershell'
$result = Invoke-WebRequest $url
$array=@($result.AllElements | Where Class -eq “st”).innerText
foreach($palabra in $ficheropalabras)
{
for($i=0;$i -lt $array.Length;$i++)
{
if($array[$i] -match $palabra){
Write-Host 'La palabra:' $palabra 'se ha encontrado posición: ' ($i+1) `n'Texto: ' $array[$i]
}
}
}

```
