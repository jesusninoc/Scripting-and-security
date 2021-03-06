# Análisis de conexiones TCP con Wireshark
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/03/analisis-de-conexiones-tcp-con-wireshark/
```PowerShell
##Client
$port=5556
$TcpClient=New-Object System.Net.Sockets.TcpClient "192.168.1.56", $port

$GetStream = $TcpClient.GetStream()
$StreamWriter = New-Object System.IO.StreamWriter $GetStream

$positions='Hi you'

$StreamWriter.Write($positions)

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
```PowerShell
##Server
$port=5556
$IPEndPoint=New-Object System.Net.IPEndPoint([System.Net.IPAddress]::any,$port)
#The TcpListener class provides simple methods that listen for and accept incoming connection requests in blocking synchronous mode. You can use either a TcpClient or a Socket to connect with a TcpListener. Create a TcpListener using an IPEndPoint, a Local IP address and port number, or just a port number. Specify Any for the local IP address and 0 for the local port number if you want the underlying service provider to assign those values for you. If you choose to do this, you can use the LocalEndpoint property to identify the assigned information, after the socket has connected.
$TcpListener=New-Object System.Net.Sockets.TcpListener $IPEndPoint
#Use the Start method to begin listening for incoming connection requests. Start will queue incoming connections until you either call the Stop method or it has queued MaxConnections. Use either AcceptSocket or AcceptTcpClient to pull a connection from the incoming connection request queue. These two methods will block. If you want to avoid blocking, you can use the Pending method first to determine if connection requests are available in the queue.
$TcpListener.Start()

$AcceptTcpClient=$TcpListener.AcceptTcpClient()
$GetStream=$AcceptTcpClient.GetStream()
$StreamReader=New-Object System.IO.StreamReader $GetStream
$StreamReader.ReadLine()

$StreamReader.Dispose()
$GetStream.Dispose()
$AcceptTcpClient.Dispose()
#Call the Stop method to close the TcpListener.
$TcpListener.Stop()

```
