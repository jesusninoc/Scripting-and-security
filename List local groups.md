# List local groups
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/07/04/list-local-groups/
```PowerShell
$adsi = [ADSI]"WinNT://$env:COMPUTERNAME"
$adsi.Children | Where-Object {$_.SchemaClassName  -eq 'group'} | Select-Object name

```
