# Send the cursor’s position between client and server (Sockets TCP)
## Network, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2015/07/08/send-the-cursors-position-between-client-and-server-sockets-tcp/
```PowerShell
##Server
while(1){
$port=2050
$IPEndPoint=New-Object System.Net.IPEndPoint([IPAddress]::Any,$port)
$TcpListener=New-Object System.Net.Sockets.TcpListener $IPEndPoint
$TcpListener.Start()
$AcceptTcpClient=$TcpListener.AcceptTcpClient()
$GetStream=$AcceptTcpClient.GetStream()
$StreamReader=New-Object System.IO.StreamReader $GetStream
$positions=$StreamReader.ReadLine()
$positions
$x=[Int]$positions.Split(‘,’)[0]
$y=[Int]$positions.Split(‘,’)[1]+100
[System.Windows.Forms.Cursor]::Position=New-Object System.Drawing.Point($x,$y)

$StreamReader.Dispose()
$GetStream.Dispose()
$AcceptTcpClient.Dispose()
$TcpListener.Stop()
}

```
```PowerShell
#Client
$port=2050
$TcpClient=New-Object System.Net.Sockets.TcpClient([IPAddress]::Loopback, $port)

$GetStream = $TcpClient.GetStream()
$StreamWriter = New-Object System.IO.StreamWriter $GetStream

$x=([System.Windows.Forms.Cursor]::Position).x
$y=([System.Windows.Forms.Cursor]::Position).y
$positions=$x.ToString()+’,’+$y.ToString()
$positions

$StreamWriter.Write($positions)

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
