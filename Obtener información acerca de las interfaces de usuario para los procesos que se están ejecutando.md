# Obtener información acerca de las interfaces de usuario para los procesos que se están ejecutando
## PowerShell, Processes 
### URL: https://www.jesusninoc.com/2016/02/05/obtener-informacion-acerca-de-las-interfaces-de-usuario-para-los-procesos-que-se-estan-ejecutando/
```PowerShell
Add-Type -AssemblyName UIAutomationClient

$procesos= Get-Process
$procesos| %{
$_
[System.Windows.Automation.AutomationElement]::FromHandle(($_).MainWindowHandle).Current
#Start-Sleep -Seconds 3
}

```
