# Add an IPv4 address
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/10/add-ipv4-address/
```PowerShell
New-NetIPAddress –InterfaceIndex 12 –IPAddress 192.168.0.16 -PrefixLength 24 -DefaultGateway 192.168.0.1

```
