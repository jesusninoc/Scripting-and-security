# Poner un color a un proceso
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2014/04/10/poner-un-color-un-proceso/
```PowerShell
$a = Read-Host “Nombre proceso a buscar”
foreach ($ap in Get-Content "F:\pcs.txt")
{
foreach ($i in Get-Process -ComputerName $ap)
{
if ($i.name -eq $a)
{
Write-Host $ap $i.name –foregroundcolor “green”
}
}
}

```
