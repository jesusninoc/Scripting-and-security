# Conectar con una URL en Java
## Java, Network 
### URL: https://www.jesusninoc.com/2012/09/21/conectar-con-una-url-en-java/
```Java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.URL;
import java.net.URLConnection;

public class ConnectionURL
{
	public static void main(String[] args) throws IOException
	{
		URL url = new URL("http://www.jesusninoc.com");
		String inputLine;
		
		URLConnection hc = url.openConnection();
		BufferedReader br = new BufferedReader(new InputStreamReader(hc.getInputStream()));
		while ((inputLine = br.readLine()) != null)
		{
			System.out.println(inputLine);
		}
		br.close();
	}
}

```
