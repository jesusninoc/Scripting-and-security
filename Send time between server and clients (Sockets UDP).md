# Send time between server and clients (Sockets UDP)
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/02/05/send-time-between-server-and-clients-sockets-udp/
```PowerShell
##Server
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
[Text.Encoding]::ASCII.GetString($content)

```
```PowerShell
##Client
$port=2020
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$val=date
$b=[Text.Encoding]::ASCII.GetBytes($val.ToString())
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
