# Ejemplos de uso de cadenas (parte 2)
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/09/28/ejemplos-de-uso-de-cadenas-parte-2/
```PowerShell
$cadena="7+1=r"
$operando1=$cadena.Substring(0,1)
$operacion1=$cadena.Substring(1,1)
$operando2=$cadena.Substring(2,1)
$operacion2=$cadena.Substring(3,1)
$operando3=$cadena.Substring(4,1)

$operando1
$operacion1
$operando2
$operacion2
$operando3

$operando3=[int]$operando1+[int]$operando2
$operando3

```
