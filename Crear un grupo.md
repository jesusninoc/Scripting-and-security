# Crear un grupo
## PowerShell, Users 
### URL: https://www.jesusninoc.com/2016/06/22/crear-un-grupo/
```PowerShell
#Nombre del equipo
$ComputerName = $env:COMPUTERNAME
$computer = [ADSI]"WinNT://$($ComputerName),computer"

#Nombre del grupo
$Name = 'grupo'
$user = $computer.Create('Group', "$($Name)")
$user.SetInfo()

```
