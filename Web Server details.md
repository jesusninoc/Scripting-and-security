# Web Server details
## PowerShell, Security, Web, Web scraping 
### URL: https://www.jesusninoc.com/2016/07/21/web-server-details/
```PowerShell
$url="https://sitecheck.sucuri.net/results/www.jesusninoc.com/"
$result = Invoke-WebRequest $url
$result.AllElements | Where class -eq “panel panel-default” | %{$_.innerText}

```
