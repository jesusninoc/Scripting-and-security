# Contar el número de ficheros que hay en un directorio cada 10 segundos
## PowerShell 
### URL: https://www.jesusninoc.com/2016/04/25/contar-el-numero-de-ficheros-que-hay-en-un-directorio-cada-10-segundos/
```PowerShell
(Get-ChildItem D:).count;Start-Sleep -Seconds 10

```
