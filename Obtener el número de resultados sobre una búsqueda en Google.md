# Obtener el número de resultados sobre una búsqueda en Google
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/02/obtener-el-numero-de-resultados-sobre-una-busqueda-en-google/
```PowerShell
$url='https://www.google.es/search?q=powershell'
$result = Invoke-WebRequest $url
$result.AllElements | Where Class -eq “sd” | %{$_.innerText}

```
