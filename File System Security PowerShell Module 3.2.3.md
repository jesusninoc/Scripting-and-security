# File System Security PowerShell Module 3.2.3
## Filesystem, Permissions, PowerShell 
### URL: https://www.jesusninoc.com/2015/07/11/file-system-security-powershell-module-3-2-3/
```PowerShell
dir | Get-Ace -ExcludeInherited | Remove-Ace

```
```PowerShell
#to backup permissions just pipe what Get-Ace returns to Export-Csv
dir | Get-Ace -ExcludeInherited | Export-Csv permissions.csv

#to retore the permissions pipe the imported data to Add-Ace
#As the imported data also contains the path you do not need to specify the item
Restore: Import-Csv .\permissions.csv | Add-Ace

```
```PowerShell
Get-Item .\VMWare | Add-Ace -Account Contoso\JohnD -AccessRights FullControl

```
```PowerShell
Get-Item F:\backup | Get-Ace –ExcludeInherited

```
```PowerShell
Get-Item F:\backup | Get-Ace | Where-Object { $_.ID -like "*users*" }

```
```PowerShell
dir -Recurse | Get-OrphanedAce | Remove-Ace

```
```PowerShell
ACEs coming from Get-Ace or Get-Get-OrphanedAce

```
```PowerShell
Get-Item F:\backup | Get-EffectivePermissions -Account S-1-5-32-545

```
```PowerShell
Get-Item .\Data -Recurse | Enable-Inheritance

```
```PowerShell
dir -Recurse | Get-Owner

```
```PowerShell
Get-Item .\Data | Set-Owner -Account builtin\administrators

```
