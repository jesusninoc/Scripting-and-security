# Mostrar enlaces de una web en PowerShell usando JavaScript
## JavaScript, PowerShell, Web 
### URL: https://www.jesusninoc.com/2016/03/27/mostrar-enlaces-de-una-web-en-powershell-usando-javascript/
```PowerShell
$ie = New-Object -com "InternetExplorer.Application"
$ie.Navigate("About:blank")
$ie.visible = $true

$web=([System.Net.WebRequest]::Create("https://www.jesusninoc.com/")).GetResponse().GetResponseStream()
$contenidoweb=New-Object System.IO.StreamReader $web
$htmlnew=$contenidoweb.ReadToEnd()+'<script>var links = document.links; for(var i=0;i<links.length;i++){alert(links[i].href);}</script>'

$ie.Document.write($htmlnew)

```
