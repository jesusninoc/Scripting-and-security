# Read file with YQL querys and show titles
## PowerShell 
### URL: https://www.jesusninoc.com/2014/02/20/read-file-with-yql-querys-and-show-titles/
```PowerShell
#IMPORTANT
#Save url in fic.txt
#https://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20html%20where%20url%3D%22http%3A%2F%2Fwww.jesusninoc.com%2Fblog%2F%22%20and%20xpath%3D'%2Fhtml%2Fhead%2Ftitle'&format=json

foreach($urls in Get-Content .fic.txt)
{
$result=(Invoke-WebRequest -Uri $urls)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
foreach($i in $convi)
{$a=$i.query.results
$a.title}
}

```
