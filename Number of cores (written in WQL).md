# Number of cores (written in WQL)
## Hardware, PowerShell 
### URL: https://www.jesusninoc.com/2015/11/22/number-of-cores-written-in-wql/
```PowerShell
Get-WmiObject -query "select NumberOfCores from Win32_Processor"

```
