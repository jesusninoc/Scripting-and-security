# Saber si un programa está instalado
## PowerShell 
### URL: https://www.jesusninoc.com/2015/08/26/saber-si-un-programa-esta-instalado/
```PowerShell
Get-Package | %{if($_.name -match 'FileZilla'){$_}}

```
