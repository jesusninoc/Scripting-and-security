# Extract the Alexa Global Rank with PowerShell
## Automation, PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/08/08/extract-the-alexa-global-rank-with-powershell/
```PowerShell
$url="https://www.alexa.com/siteinfo/jesusninoc.com"
$result = Invoke-WebRequest $url
($result.AllElements | Where class -eq “metrics-data align-vmiddle”)[0].innerText

```
