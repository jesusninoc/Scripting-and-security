# Obtener información de los resultados sobre las búsquedas en Google Hacking Database
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/04/01/obtener-informacion-de-los-resultados-sobre-las-busquedas-en-google-hacking-database/
```PowerShell
#Buscar los últimos dorks en https://www.exploit-db.com/google-hacking-database/
(Invoke-WebRequest 'https://www.exploit-db.com/google-hacking-database/').AllElements | %{$_.href | Select-String https://www.exploit-db.com/ghdb/} | %{
#Para cada enlace obtener el contenido del dork (where class “l-titlebar-h i-cf”)
$buscar=((Invoke-WebRequest $_.tostring()).AllElements | Where class -eq “l-titlebar-h i-cf”).outerText
$buscar
$url='https://www.google.es/search?q='+$buscar
$url
#Buscar en Google el dork
((Invoke-WebRequest $url).AllElements | Where Class -eq “g”).outerText | %{
Start-Sleep -Seconds 5
$_
}
}

```
