# Displays the common properties for the network adapter named Wi-Fi
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/04/displays-common-properties-network-adapter-named-wi-fi/
```PowerShell
Get-NetAdapter –Name 'Wi-Fi' | Format-List –Property *

```
