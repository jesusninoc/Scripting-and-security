# Read domain list and try to connect
## PowerShell, Security, Servers 
### URL: https://www.jesusninoc.com/2014/01/27/read-domain-list-and-try-to-connect/
```PowerShell
#Read domains
foreach ($i in Get-Content .\fichero2.txt)
{
    (Invoke-WebRequest $i).StatusCode

    #Try to connect (ports 1 to 4)
    1..4 | % {(New-Object System.Net.Sockets.TCPClient).Connect($i,$_).Connected}
}

```
