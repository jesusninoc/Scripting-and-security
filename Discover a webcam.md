# Discover a webcam
## PowerShell 
### URL: https://www.jesusninoc.com/2017/10/17/discover-a-webcam/
```PowerShell
Get-PnpDevice | where {$_.FriendlyName -match 'cam'}

```
# Discover a webcam
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/06/19/discover-webcam/
```PowerShell
Get-WmiObject Win32_PnPEntity | where {$_.caption -match 'webcam'}

```
