# Extract all the elements of a web page
## PowerShell, Security, Web 
### URL: https://www.jesusninoc.com/2014/02/05/extract-all-the-elements-of-a-web-page/
```PowerShell
$a=Invoke-WebRequest “https://www.jesusninoc.com/powershell"
$a.AllElements

```
