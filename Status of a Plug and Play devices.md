# Status of a Plug and Play devices
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/06/23/status-of-a-plug-and-play-device/
```PowerShell
(Get-CimInstance Win32_PnPEntity) | Select-Object Name, Status

```
