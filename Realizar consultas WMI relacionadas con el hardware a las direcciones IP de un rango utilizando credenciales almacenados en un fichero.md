# Realizar consultas WMI relacionadas con el hardware a las direcciones IP de un rango utilizando credenciales almacenados en un fichero
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2016/08/24/realizar-consultas-wmi-relacionadas-con-el-hardware-a-las-direcciones-ip-de-un-rango-utilizando-credenciales-almacenados-en-un-fichero/
```PowerShell
$credenciales=Import-Clixml -Path credenciales.xml
1..254 | %{
    (Get-WmiObject Win32_AutochkSetting -ComputerName ('192.168.1.'+$_) -Credential $credenciales).SettingID
    (Get-WmiObject Win32_BaseBoard -ComputerName ('192.168.1.'+$_) -Credential $credenciales).Manufacturer
    (Get-WmiObject Win32_BIOS -ComputerName ('192.168.1.'+$_) -Credential $credenciales).Version
    (Get-WmiObject Win32_Bus -ComputerName ('192.168.1.'+$_) -Credential $credenciales).DeviceID
    Get-WmiObject Win32_Processor -ComputerName ('192.168.1.'+$_) -Credential $credenciales
    Get-WmiObject Win32_SystemEnclosure -ComputerName ('192.168.1.'+$_) -Credential $credenciales
    Get-WmiObject Win32_Battery -ComputerName ('192.168.1.'+$_) -Credential $credenciales
    Get-WmiObject Win32_Printer -ComputerName ('192.168.1.'+$_) -Credential $credenciales
}

```
