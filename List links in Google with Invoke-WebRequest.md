# List links in Google with Invoke-WebRequest
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2013/01/01/list-links-in-google-with-invoke-webrequest/
```PowerShell
$urls="https://www.google.com/search?q=powershell"
$result=Invoke-WebRequest $urls
$en=$result.AllElements | ? {$_.tagName -eq "cite"}

foreach($aen in $en.innerText){
    $aen
}

```
