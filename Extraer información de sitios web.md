# Extraer información de sitios web
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2016/01/25/extraer-informacion-de-sitios-web/
```PowerShell
$url='https://www.bbc.com/news/'
$result = Invoke-WebRequest $url
$result.Content

```
```PowerShell
$url='https://www.bbc.com/news/'
$result = Invoke-WebRequest $url
$result.Content
$result.AllElements | Where Class -eq 'title-link__title-text' | %{$_.innerText}

```
