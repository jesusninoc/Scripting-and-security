# Abrir URL en PowerShell cambiando el User-Agent
## PowerShell 
### URL: https://www.jesusninoc.com/2016/05/24/abrir-url-en-powershell-cambiando-el-user-agent/
```PowerShell
(Invoke-WebRequest "https://jesusninoc.com" -UserAgent "Mozilla/5.0 (Windows NT 6.3; WOW64)").Content

```
