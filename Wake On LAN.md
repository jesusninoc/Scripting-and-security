# Wake On LAN
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2015/02/23/wake-lan/
```PowerShell
#Wake-on-LAN (WoL) is an Ethernet computer networking standard that allows a computer to be turned on or awakened by a network message.
$MacAddress="00-11-22-33-44-55"
[byte[]] $MagicPacket = 0xFF, 0xFF, 0xFF, 0xFF, 0xFF, 0xFF
$MagicPacket += (($MacAddress.split('-') | foreach {[byte]('0x' + $_)}) * 16)
$UdpClient = New-Object System.Net.Sockets.UdpClient
$UdpClient.Connect(([System.Net.IPAddress]::Broadcast) ,9)
$UdpClient.Send($MagicPacket,$MagicPacket.length)

```
