# Searching URLs in text files
## PowerShell 
### URL: https://www.jesusninoc.com/2014/11/19/searching-urls-text-files/
```PowerShell
Write-Host "URLs:`n"
Get-ChildItem C:\Users\ -rec -ea SilentlyContinue | ForEach-Object {
# \b(ht|f)tp(s?)[^ ]*\.[^ ]*(\/[^ ]*)*\b
Select-String "(ht|f)tp(s?):\/{2}[^ ]*\.[^ ]\w{1,3}$" -input (Get-ItemProperty -Path $_.PsPath) -AllMatches | ForEach-Object {($_.matches)|Select-Object Value}
}

```
