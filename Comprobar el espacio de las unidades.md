# Comprobar el espacio de las unidades
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/31/comprobar-el-espacio-de-las-unidades/
```PowerShell
get-wmiobject win32_volume -computername . | select name, @{expression={$_.capacity/1GB}}, @{expression={$_.freespace/1GB}}, @{name=”% Free”;expression={$_.freespace/$_.capacity*100}}

```
