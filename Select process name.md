# Select process name
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2014/02/05/select-process-name/
```PowerShell
foreach($masuno in (ps | Select-Object name))
{
    $masuno.name
}

```
