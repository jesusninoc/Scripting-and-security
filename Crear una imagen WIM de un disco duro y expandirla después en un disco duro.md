# Crear una imagen WIM de un disco duro y expandirla después en un disco duro
## PowerShell 
### URL: https://www.jesusninoc.com/2015/08/02/crear-una-imagen-wim-de-un-disco-duro-y-expandirla-despues-en-un-disco-duro/
```PowerShell
New-WindowsImage -ImagePath "f:\imagen.wim" -CapturePath "d:\" -Name "Unidad d"

```
```PowerShell
Expand-WindowsImage -ImagePath "f:\imagen.wim" -ApplyPath "d:\" -Index 1

```
