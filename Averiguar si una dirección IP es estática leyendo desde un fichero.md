# Averiguar si una dirección IP es estática leyendo desde un fichero
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/21/averiguar-si-una-direccion-ip-es-estatica-leyendo-desde-un-fichero/
```PowerShell
gc D:\ips.txt | %{
$result=(Resolve-DnsName $_).NameHost
if($result -match 'static'){$_ + ' static'}
else{$result + ' no static'}
}

```
