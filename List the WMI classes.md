# List the WMI classes
## PowerShell 
### URL: https://www.jesusninoc.com/2014/12/08/list-wmi-classes/
```PowerShell
Get-WmiObject -list -recurse

```
```PowerShell
(Get-WmiObject -list -recurse).count

```
