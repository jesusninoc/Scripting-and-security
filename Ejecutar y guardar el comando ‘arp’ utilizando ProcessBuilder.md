# Ejecutar y guardar el comando ‘arp’ utilizando ProcessBuilder
## Java, Network 
### URL: https://www.jesusninoc.com/2015/10/11/ejecutar-y-guardar-el-comando-arp-utilizando-processbuilder/
```Java
import java.io.IOException;

public class ProcesoArp
{
	public static void main(String[] args)
	{
		ProcessBuilder pb = new ProcessBuilder("cmd", "/C", "arp -a > F:\\java\\arp.txt");
		try
		{
			pb.start();
		}
		catch (IOException e)
		{
			System.out.println(e.getMessage());
		}
	}
}

```
