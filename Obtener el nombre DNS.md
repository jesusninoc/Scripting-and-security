# Obtener el nombre DNS
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/09/12/obtener-el-nombre-dns/
```PowerShell
$ip='8.8.8.8'
(Resolve-DnsName $ip).NameHost

```
