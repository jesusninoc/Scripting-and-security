# Add users
## PowerShell 
### URL: https://www.jesusninoc.com/2012/12/29/add-users/
```PowerShell
New-Item -ItemType "file" -path . -name "users" -value "Juan Pedro Pablo Victor Mateo"
$user=Get-content "./users"
foreach ($a in $user)
{
$psw=-join ([Char[]]'abcdefgABCDEFG0123456&%$' | Get-Random -count 14)
net user $a $psw /add
}

```
