# Reading username and password from file and do a login
## PowerShell, Security, Users 
### URL: https://www.jesusninoc.com/2014/03/10/reading-username-and-password-from-file-and-do-a-login/
```PowerShell
#Read user and password
$user=Read-Host
$pass=Read-Host

#Read user.txt, example content:
#user1,passwoasdfK$
Get-Content F:\power\users.txt | % {if(($_.split(",")[0] -like $user) -and ($_.split(",")[1] -like $pass)){"Login OK"}}

```
