# Emitir un sonido por el altavoz del equipo
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/04/05/emitir-un-sonido-por-el-altavoz-del-equipo/
```PowerShell
#https://msdn.microsoft.com/es-es/library/kz27k38z(v=vs.90).aspx

Add-Type -AssemblyName Microsoft.VisualBasic

[Microsoft.VisualBasic.Interaction]::Beep()

```
