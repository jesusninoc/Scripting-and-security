# UDP system access
## Network, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2014/02/18/udp-system-access/
```PowerShell
##Server
$port=2021
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Any,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient $port
$content=$udpclient.Receive([ref]$endpoint)
$convert=[Text.Encoding]::ASCII.GetString($content)
$spli=$convert.Split("*")
$user=$spli[0]
$pass=$spli[1]
if($user -eq "user" -and $pass -eq "pass")
{
Write-Host "Login"
}
else
{
Write-Host "No login"
}
$udpclient.Close()

```
```PowerShell
##Client
$port=2021
$endpoint = new-object System.Net.IPEndPoint ([IPAddress]::Loopback,$port)
$udpclient=new-Object System.Net.Sockets.UdpClient
$val="user*pass"
$b=[Text.Encoding]::ASCII.GetBytes($val.ToString())
$bytesSent=$udpclient.Send($b,$b.length,$endpoint)
$udpclient.Close()

```
