# Get entries from the IPv4 neighbor cache
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2016/05/02/get-entries-from-the-ipv4-neighbor-cache/
```PowerShell
Get-NetNeighbor | Where-Object AddressFamily -EQ IPv4

```
