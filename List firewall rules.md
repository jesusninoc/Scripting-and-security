# List firewall rules
## Network, PowerShell 
### URL: https://www.jesusninoc.com/2015/03/14/list-firewall-rules/
```PowerShell
#Direction: Inbound
Get-NetFirewallRule | Where {$_.Direction –eq ‘Inbound’}

```
