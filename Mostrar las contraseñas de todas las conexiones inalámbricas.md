# Mostrar las contraseñas de todas las conexiones inalámbricas
## Network, PowerShell, Security, Wireless 
### URL: https://www.jesusninoc.com/2016/05/25/mostrar-las-contrasenas-de-todas-las-conexiones-inalambricas/
```PowerShell
(netsh wlan show profile | Select-String "Perfil de todos los usuarios") | %{
[String]$SSID=$_
$SSID=$SSID.Split(":")[1].trim()
$SSID
netsh wlan show profile name=$SSID key=clear | Select-String 'Contenido de la clave'
}

```
