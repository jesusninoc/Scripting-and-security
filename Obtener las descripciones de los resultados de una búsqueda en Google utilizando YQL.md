# Obtener las descripciones de los resultados de una búsqueda en Google utilizando YQL
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/17/obtener-las-descripciones-de-los-resultados-de-una-busqueda-en-google-utilizando-yql/
```PowerShell
$urls='https://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20google.search%20where%20q%20%3D%20%22powershell%22&format=json&env=store%3A%2F%2Fdatatables.org%2Falltableswithkeys&callback='
((Invoke-WebRequest -Uri $urls).Content | ConvertFrom-JSON).query.results.results.content

```
