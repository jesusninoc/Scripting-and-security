# Get hardware info
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/15/get-hardware-info/
```PowerShell
$computer='.'
Get-WmiObject Win32_BIOS –computername $computer
Get-WmiObject Win32_ComputerSystem -cn $computer
Get-WmiObject Win32_Processor –computername $computer

```
