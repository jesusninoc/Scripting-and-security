# Crear un hilo implementando el interfaz Runnable
## Java, Processes, Threads 
### URL: https://www.jesusninoc.com/2012/08/31/crear-un-hilo-implementando-el-interfaz-runnable/
```Java
import java.util.concurrent.TimeUnit;

public class HelloRunnable implements Runnable {
	public void run() {
    	System.out.println("Ejecutando hilo");
        System.out.println(Thread.currentThread().getName());
    }
	public static void main(String args[]) {
    	System.out.println(Thread.currentThread().getName());
    	int i=0;
    	while(i<100)
    	{
        (new Thread(new HelloRunnable())).start();
    	try {
			TimeUnit.SECONDS.sleep(10);
		} catch (InterruptedException e) {
			e.printStackTrace();
		}
        i++;
    	}
    }
}

```
