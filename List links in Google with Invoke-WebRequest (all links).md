# List links in Google with Invoke-WebRequest (all links)
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2015/03/21/list-links-in-google-with-invoke-webrequest-all-links/
```PowerShell
$urls='https://www.google.com/search?q=jesusninoc'
$result=Invoke-WebRequest $urls
$en=$result.AllElements | ? {$_.tagName -eq 'a'}
foreach($aen in $en){
$aen.href
}

```
