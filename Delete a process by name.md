# Delete a process by name
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2012/10/25/delete-a-process-by-name/
```PowerShell
[string]$n="notepad"
Start-Process $n

start-sleep -Milliseconds 555

$proces=Get-Process
foreach ($g in $proces)
{
    [string]$h=""
    $h=$g.ProcessName

    if ($h.contains($n))
    {
        Stop-Process -name $h
    }
}

```
