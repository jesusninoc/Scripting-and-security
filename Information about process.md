# Information about process
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2014/03/04/information-process/
```PowerShell
#Getting process list
foreach($proces in get-process)
{
#Process information
$proceso=$proces.Name+".exe"
$url=”https://elarchivo.es/proceso/”+$proceso+”.html”
((Invoke-WebRequest $url).AllElements | Where Class -eq “legend” | Select -ExpandProperty innerText)[1]
}

```
