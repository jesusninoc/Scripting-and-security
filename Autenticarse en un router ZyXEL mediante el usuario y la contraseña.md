# Autenticarse en un router ZyXEL mediante el usuario y la contraseña
## Automation, Network, PowerShell, Security 
### URL: https://www.jesusninoc.com/2015/12/11/autenticarse-en-un-router-zyxel-mediante-el-usuario-y-la-contrasena/
```PowerShell
$user="admin"
$pass="admin123"
$pair="${user}:${pass}"
$bytes=[System.Text.Encoding]::ASCII.GetBytes($pair)
$base64=[System.Convert]::ToBase64String($bytes)
$basicAuthValue="Basic $base64"
$headers=@{Authorization=$basicAuthValue}

$url='http://192.168.1.1:89/rpSys.html'
$result=(Invoke-WebRequest -Uri $url -Headers $headers)
($result.AllElements | Where tagName -eq “title”).outerText

```
