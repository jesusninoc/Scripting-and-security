# Seleccionar y devolver un valor de una lista de argumentos
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/02/13/seleccionar-y-devolver-un-valor-de-una-lista-de-argumentos/
```PowerShell
#https://msdn.microsoft.com/es-es/library/824bz7dy(v=vs.90).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

[Microsoft.VisualBasic.Interaction]::Choose(2,"Uno", "Dos", "Tres")

```
