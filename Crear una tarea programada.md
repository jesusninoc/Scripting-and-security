# Crear una tarea programada
## PowerShell, Schedule tasks 
### URL: https://www.jesusninoc.com/2016/04/19/crear-una-tarea-programada/
```PowerShell
Register-ScheduledTask Task01 -Action (New-ScheduledTaskAction -Execute "Cmd") -Principal (New-ScheduledTaskPrincipal -GroupId "BUILTIN\administradores" -RunLevel Highest) -Settings (New-ScheduledTaskSettingsSet -RestartCount 5 -RestartInterval 60)

```
