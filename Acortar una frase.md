# Acortar una frase
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2016/04/14/acortar-una-frase/
```PowerShell
$longitud=20
$procesar=’En cierto lugar de mi casa’

if($procesar.Length -gt $longitud)
{
$procesar.Substring(0,$longitud) + '...'
}
else
{
$procesar
}

```
