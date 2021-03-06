# Server and client (Sockets TCP)
## Java, Network 
### URL: https://www.jesusninoc.com/2012/10/11/server-and-client-sockets-tcp-2/
```Java
import java.io.*; 
import java.net.*;

public class Server
{
	public static void main(String[] args)
	{
		int port=2050;
		try
		{
			ServerSocket serverSocket = new ServerSocket(port);
			
			Socket clientSocket = serverSocket.accept();
			
			PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
			BufferedReader in = new BufferedReader(new InputStreamReader (clientSocket.getInputStream()));
			
			String inputLine = in.readLine();
			System.out.println("Receive: " + inputLine); 
			String outputLine = inputLine.toUpperCase(); 
			System.out.println("Send: " + outputLine); 
			out.println(outputLine); 
			
			out.close(); 
			in.close(); 
			
			clientSocket.close(); 
			serverSocket.close();
			}
		catch (UnknownHostException e){
			System.out.println(e);
		} catch (IOException e) {
			System.out.println(e);
		}
		}
	}

```
```Java
import java.io.*; 
import java.net.*;

public class Client
{
	public static void main(String[] args)
	{
		int port=2050;
		try
		{
			Socket clientSocket = new Socket("192.168.1.37",port);
			
			PrintWriter out = new PrintWriter(clientSocket.getOutputStream(),true);
			BufferedReader in = new BufferedReader(new InputStreamReader (clientSocket.getInputStream()));
			
			System.out.println("Send: Hi"); 
			out.println("Hi");
			System.out.println("Receive: " + in.readLine());
			
			out.close();
			in.close();
			clientSocket.close();
			}
		catch (UnknownHostException e){
			System.out.println(e);
		}
		catch (IOException e) {
			System.out.println(e);
		}
		}
	}

```
# Server and client (Sockets TCP)
## Network, PowerShell, Servers 
### URL: https://www.jesusninoc.com/2013/01/02/server-and-client-sockets-tcp/
```PowerShell
##Server
$port=2050
$IPEndPoint=New-Object System.Net.IPEndPoint([IPAddress]::Any,$port)
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
```PowerShell
##Client
$port=2050
$TcpClient=New-Object System.Net.Sockets.TcpClient([IPAddress]::Loopback, $port)

$GetStream = $TcpClient.GetStream()
$StreamWriter = New-Object System.IO.StreamWriter $GetStream

$positions='Hi'

$StreamWriter.Write($positions)

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
```PowerShell
##Client
$port=2050
$TcpClient=New-Object System.Net.Sockets.TcpClient "192.168.1.56", $port

$GetStream = $TcpClient.GetStream()
$StreamWriter = New-Object System.IO.StreamWriter $GetStream

$positions='Hi'

$StreamWriter.Write($positions)

$StreamWriter.Dispose()
$GetStream.Dispose()
$TcpClient.Dispose()

```
