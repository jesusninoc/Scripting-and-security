# Transfer images between server and client (Sockets TCP)
## Network, PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2015/11/07/transfer-images-between-server-and-client-sockets-tcp/
```PowerShell
$endpoint = new-object System.Net.IPEndPoint ([system.net.ipaddress]::any, 8982)
$listener = new-object System.Net.Sockets.TcpListener $endpoint
$listener.start()
$contador=0
do {
$client = $listener.AcceptTcpClient() # will block here until connection
$stream = $client.GetStream();

$reader = New-Object System.IO.StreamReader $stream

$lines=$reader.ReadToEnd()

$enc = [system.Text.Encoding]::Default
$filebytes = $enc.GetBytes($lines)

$contador=$contador+1
[System.IO.File]::WriteAllBytes('F:\power\video\capturas2\'+$contador+'.bmp', $filebytes)

$reader.Dispose()
$stream.Dispose()
$client.Dispose()

} while (1)

```
```PowerShell
function send-msg($file)
{
$client = New-Object System.Net.Sockets.TcpClient "localhost", 8982
$stream = $client.GetStream()
$writer = New-Object System.IO.StreamWriter $stream

$bytes = [System.IO.File]::ReadAllBytes($file)
#$writer.WriteLine($bytes)
$writer.Write($bytes,0,$bytes.length)
$writer.Dispose()
$stream.Dispose()
$client.Dispose()
}

ls F:\power\video\captura\ | %{send-msg($_.FullName)}

```
