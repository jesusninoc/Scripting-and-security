# Identificar la dirección IP de las contribuciones del usuario en Wikipedia y analizar información de la dirección IP
## Database, PowerShell, Servers 
### URL: https://www.jesusninoc.com/2015/01/01/identificar-la-direccion-ip-de-las-contribuciones-del-usuario-en-wikipedia-y-analizar-informacion-de-la-direccion-ip/
```PowerShell
Get-Content 'F:\power\ips\listado.txt' | % {

#Query the APNIC Whois Database
$url='https://wq.apnic.net/apnic-bin/whois.pl?searchtext='+$_
$url
$result = Invoke-WebRequest $url
$whois=$result.AllElements | Where tagName -eq “pre” | %{$_.innerText}
$fichero='F:\power\'+$_.replace(".","")+'.txt'
$whois | Out-File $fichero -Append
sleep -Seconds 5

#User contributions Wikipedia
$url='https://es.wikipedia.org/wiki/Especial:Contribuciones/'+$_
$url
$result = Invoke-WebRequest $url
$wikipedia=$result.AllElements | Where Class -eq “mw-contributions-list” | %{$_.innerText}
$fichero='F:\power\'+$_.replace(".","")+'.txt'
$wikipedia | Out-File $fichero -Append
sleep -Seconds 5
}

```
