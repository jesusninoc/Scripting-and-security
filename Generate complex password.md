# Generate complex password
## PowerShell, Security, Web 
### URL: https://www.jesusninoc.com/2015/06/07/generate-complex-password/
```PowerShell
$Assembly = Add-Type -AssemblyName System.Web
[System.Web.Security.Membership]::GeneratePassword(10,3)

```
