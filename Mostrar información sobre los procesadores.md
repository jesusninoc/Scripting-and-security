# Mostrar información sobre los procesadores
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/10/13/mostrar-informacion-sobre-los-procesadores/
```PowerShell
Get-WmiObject -Class Win32_Processor | Select -Property Name, Number*

```
