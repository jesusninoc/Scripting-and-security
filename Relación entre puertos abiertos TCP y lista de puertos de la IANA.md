# Relación entre puertos abiertos TCP y lista de puertos de la IANA
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/02/29/relacion-entre-puertos-abiertos-tcp-y-lista-de-puertos-de-la-iana/
```PowerShell
#Descargar y guardar el listado de puertos
Invoke-WebRequest 'https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.csv' -OutFile d:\service-names-port-numbers.csv

#Relación entre puertos abiertos TCP y lista de puertos la IANA
$portscsv=Import-Csv d:\service-names-port-numbers.csv
$listado=$portscsv | Select-Object 'Service Name','Port Number','Transport Protocol' | Where-Object 'Transport Protocol' -EQ tcp
Get-NetTCPConnection | Select-Object Localaddress,Remoteport,Remoteaddress | %{$_.Localaddress; $listado | Select-Object 'Service Name','Port Number' | Where-Object 'Port Number' -EQ $_.RemotePort;$_.Remoteaddress} | Format-Custom

```
