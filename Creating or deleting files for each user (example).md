# Creating or deleting files for each user (example)
## Filesystem, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/21/creating-deleting-files-user-example/
```PowerShell
#Creating or deleting files for each user
Set-Location F:\power\
#User and operation list in a file
#Example:
#Juan,create
#Lucas,delete
ForEach($user in Get-Content .\namesandoperation.txt)
{
if($user.Split(',')[1] -match 'create')
{
Write-Host 'Create file'
$user=$user.Split(',')[0]
#Creating file for each user
#If the item you are trying to create already exists
#Override the default behavior
New-Item $user'.txt' -ItemType file -Force
}
if($user.Split(',')[1] -match 'delete')
{
Write-Host 'Delete file'
$user=$user.Split(',')[0]
#Deleting file for each user
Remove-Item $user'.txt'
}
}

```
