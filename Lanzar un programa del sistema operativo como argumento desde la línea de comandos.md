# Lanzar un programa del sistema operativo como argumento desde la línea de comandos
## Java, Processes 
### URL: https://www.jesusninoc.com/2012/08/28/lanzar-un-programa-del-sistema-operativo-como-argumento-desde-la-linea-de-comandos/
```Java
import java.io.IOException;

public class Proceso
{
	public static void main(String[] args) throws IOException
	{
		ProcessBuilder pb = new ProcessBuilder(args);
		pb.start();
	}
}

```
