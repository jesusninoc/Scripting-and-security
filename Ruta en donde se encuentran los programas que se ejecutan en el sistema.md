# Ruta en donde se encuentran los programas que se ejecutan en el sistema
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2015/01/30/ruta-en-donde-se-encuentran-los-programas-que-se-ejecutan-en-el-sistema/
```PowerShell
Get-WmiObject win32_process -co . | Select-Object CSName,Description,Processid,WS,Path | Sort-Object WS -Descending | Format-Table * -AutoSize

```
