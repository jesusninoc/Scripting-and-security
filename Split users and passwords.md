# Split users and passwords
## PowerShell 
### URL: https://www.jesusninoc.com/2013/02/07/split-users-and-passwords/
```PowerShell
"javier:1234#2@aa" | Out-File alum.txt

$usuarios=Get-Content alum.txt
foreach($i in $usuarios)
{
    $partir=$i.Split(":")
    $partir[0]
    $partir[1]
}

```
