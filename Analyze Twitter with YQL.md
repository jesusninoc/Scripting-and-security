# Analyze Twitter with YQL
## PowerShell 
### URL: https://www.jesusninoc.com/2014/02/21/analyze-twitter-yql/
```PowerShell
#URL twitter.com/microsoft

$ur="https://query.yahooapis.com/v1/public/yql?q=select%20*%20from%20html%20where%20url%3D%22https%3A%2F%2Ftwitter.com%2Fmicrosoft%22&format=json&callback="
$result=(Invoke-WebRequest -Uri $ur)
$conv=$result.Content
$convi = $conv | ConvertFrom-JSON
foreach($i in $convi.query.results.body.div[0].div[1].div[0].div[4].div[1].div[0].ol.li){
$span = $i.div[0].div[1].p.content
$span
}

```
