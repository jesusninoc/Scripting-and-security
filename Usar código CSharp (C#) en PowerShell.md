# Usar código CSharp (C#) en PowerShell
## C#, PowerShell 
### URL: https://www.jesusninoc.com/2015/07/02/usar-codigo-csharp-c-en-powershell/
```PowerShell
$CodigoC = @"

public class Hola
{
public static void Main()
{
System.Console.WriteLine("Hola");
}
}

"@

#Importante: utilizar las comillas correctamente en la función del Main()

Add-Type -TypeDefinition $CodigoC -ErrorAction SilentlyContinue

[Hola]::Main()

```
