# Buscar una palabra en las descripciones de los resultados de una búsqueda en Yahoo
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/25/buscar-una-palabra-en-las-descripciones-de-los-resultados-de-una-busqueda-en-yahoo/
```PowerShell
$url='https://es.search.yahoo.com/search?p=powershell'
$result = Invoke-WebRequest $url
$array=@($result.AllElements | Where Class -eq “lh-18 ”).innerText
for($i=0;$i -lt $array.Length;$i++)
{
if($array[$i] -match 'scripting'){
Write-Host 'Encontrado posición: ' ($i+1) `n'Texto: ' $array[$i]
}
}

```
