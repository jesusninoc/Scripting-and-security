# Equivalencias entre comandos de red de Windows y Cmdlets de PowerShell
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/02/04/equivalencias-entre-comandos-de-red-de-windows-y-cmdlets-de-powershell/
```PowerShell
Get-NetAdapter | Select-Object Name,MacAddress
Get-WmiObject -Class Win32_NetworkAdapterConfiguration | Select-Object Description,MACAddress
Get-NetNeighbor

```
```PowerShell
Get-NetIPAddress
Get-NetIPConfiguration
Get-NetIPAddress | Sort InterfaceIndex | FT InterfaceIndex, InterfaceAlias, AddressFamily, IPAddress, PrefixLength -Autosize
Get-NetIPAddress | ? AddressFamily -eq IPv4 | FT –AutoSize
Get-NetAdapter Wi-Fi | Get-NetIPAddress | FT -AutoSize

```
```PowerShell
New-NetIPAddress -InterfaceAlias Wi-Fi -IPAddress 192.168.1.56 -PrefixLength 24 -DefaultGateway 192.168.1.1
Set-NetIPAddress –InterfaceIndex 12 –IPAddress 192.168.0.16
Remove-NetIPAddress –IPAddress 192.168.0.16 -DefaultGateway 192.168.0.1

```
```PowerShell
Get-NetTCPConnection
Get-NetTCPConnection | Group State, RemotePort | Sort Count | FT Count, Name –Autosize
Get-NetTCPConnection | ? State -eq Established | FT –Autosize
Get-NetTCPConnection | ? State -eq Established | ? RemoteAddress -notlike 127* | % { $_; Resolve-DnsName $_.RemoteAddress -type PTR -ErrorAction SilentlyContinue}
Get-NetUDPEndpoint

```
```PowerShell
Resolve-DnsName

```
```PowerShell
Test-NetConnection
Test-NetConnection www.jesusninoc.com
Test-NetConnection -ComputerName www.jesusninoc.com -InformationLevel Detailed
Test-NetConnection -ComputerName www.jesusninoc.com | Select -ExpandProperty PingReplyDetails | FT Address, Status, RoundTripTime
1..100 | % { Test-NetConnection -ComputerName www.jesusninoc.com -RemotePort 80 } | FT -AutoSize

```
```PowerShell
Get-NetRoute
Get-NetAdapter Wi-Fi | Get-NetRoute
New-NetRoute
Remove-NetRoute

```
```PowerShell
Test-NetConnection –TraceRoute

```
