# Ver actualizaciones instaladas en el sistema
## PowerShell, Updates 
### URL: https://www.jesusninoc.com/2016/09/08/ver-actualizaciones-instaladas-en-el-sistema/
```PowerShell
Get-HotFix | Select-Object HotFixID
Get-Package | Select-Object Name | Where-Object Name -match "Actualización" | Format-Custom

```
