# Enviar correo electrónico utilizando Outlook
## PowerShell 
### URL: https://www.jesusninoc.com/2015/06/05/enviar-correo-electronico-utilizando-outlook/
```PowerShell
$Outlook = New-Object -ComObject Outlook.Application
$Mail = $Outlook.CreateItem(0)
$Mail.To = "user1@gmail.com"
$Mail.Subject = "Asunto"
$Mail.Body ="Texto del mail"
$Mail.Send()

```
