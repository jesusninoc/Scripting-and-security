# Ejecutar la función hash SHA1 sobre los ficheros de un directorio y almacenar el resultado en un fichero
## Cryptography, PowerShell, Security 
### URL: https://www.jesusninoc.com/2016/01/26/ejecutar-la-funcion-hash-sha1-sobre-los-ficheros-de-un-directorio-y-almacenar-el-resultado-en-un-fichero/
```PowerShell
ls D:\power\files | % {Get-FileHash $_.FullName -Algorithm SHA1 | Out-File d:\hash.txt -Append}

```
