# Find IP Address by MAC Address
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2014/12/01/find-ip-address-mac-address/
```PowerShell
#MAC file
$macs = get-content .\mac.txt
foreach($mac in $macs){
#Use arp -a
$ip = arp -a | select-string "$mac" |% { $_.ToString().Trim().Split(" ")[0] }
"$mac has an ip of $ip"
}

```
```PowerShell
Get-NetNeighbor | Select-Object IPAddress,LinkLayerAddress

```
