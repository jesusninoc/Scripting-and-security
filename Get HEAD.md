# Get HEAD
## PowerShell, Security 
### URL: https://www.jesusninoc.com/2014/02/04/get-head/
```PowerShell
$urls=”https://www.google.com/search?q=powershell”
$result=Invoke-WebRequest $urls
$en=$result.AllElements | ? {$_.tagName -eq “cite”}

foreach($aen in $en.innerText)
{
    $resulta=Invoke-WebRequest $aen
    echo $aen
    foreach($a in $resulta.AllElements)
    {
        if($a.innerHTML.Contains(""))
        {
            $a.innerHTML
        }
    }
sleep -milliseconds 100
}

```
