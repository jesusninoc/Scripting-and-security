# Server and client (Datagram Socket UDP)
## Java, Network 
### URL: https://www.jesusninoc.com/2012/10/13/server-and-client-datagram-socket-udp/
```Java
import java.net.*;
import java.io.*;

public class ServerUDP
{
	public static void main (String args[])
	{
		try
		{
			int port = 2020;
			DatagramSocket socketUDP = new DatagramSocket(port);
			byte[] bufer = new byte[1000];
			
			while (true)
			{
				DatagramPacket send = new DatagramPacket(bufer, bufer.length);
				socketUDP.receive(send);
				String text = new String(send.getData()).trim();
				System.out.println("Receive: " + text);

				System.out.println("Send: " + text.toUpperCase());
				DatagramPacket receive = new DatagramPacket(text.toUpperCase().getBytes(), text.length(),send.getAddress(), send.getPort());
		        socketUDP.send(receive);
				
				socketUDP.close();
				}
			}
		catch (SocketException e) {}
		catch (IOException e) {}
		}
	}

```
```Java
import java.io.*; 
import java.net.*;

public class ClientUDP
{
	public static void main(String[] args)
	{
		try
		{
			int port = 2020;
			InetAddress host = InetAddress.getByName("192.168.1.37");
			String text = "Hi";
			
			DatagramSocket socketUDP = new DatagramSocket();
			System.out.println("Send: " + text);
			DatagramPacket send = new DatagramPacket(text.getBytes(), text.getBytes().length, host, port);
			socketUDP.send(send);
			
			byte[] bufer = new byte[1000];
			DatagramPacket receive = new DatagramPacket(bufer, bufer.length);
			socketUDP.receive(receive);
			System.out.println("Receive: " + new String(receive.getData()).trim());
			
			socketUDP.close();
		    }
		catch (SocketException e) {}
		catch (IOException e) {}
		}
	}

```
