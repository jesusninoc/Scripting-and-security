# Analizar permisos de un .apk
## Android, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/12/08/analizar-permisos-de-un-apk/
```PowerShell
#Utilizando Apktool (A tool for reverse engineering Android apk files) obtenemos el fichero AndroidManifest.xml en el que analizamos los permisos en un .apk

$ruta='d:\apks\AndroidManifest.xml'
[xml]$xml=gc $ruta
$xml | Format-List
$xml.manifest.'uses-permission'

```
