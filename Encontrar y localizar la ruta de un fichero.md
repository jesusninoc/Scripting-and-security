# Encontrar y localizar la ruta de un fichero
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/29/encontrar-y-localizar-la-ruta-de-un-fichero/
```PowerShell
Get-ChildItem -Recurse | % {if($_.Name | Select-String "fichero"){$_.FullName}}

```
