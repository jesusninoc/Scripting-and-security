# Ejecutar código JavaScript utilizando Start-Process y Google Chrome
## JavaScript, PowerShell 
### URL: https://www.jesusninoc.com/2016/05/21/ejecutar-codigo-javascript-utilizando-start-process-y-google-chrome/
```PowerShell
$contenido="data:text/html,<script>alert(Date())</script>"
Start-Process chrome $contenido

```
