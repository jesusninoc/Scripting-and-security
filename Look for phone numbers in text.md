# Look for phone numbers in text
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/10/09/look-phone-numbers-text/
```PowerShell
#File numers.txt contains:
#123-123-1234
#123-123-1235
#123-123-1236
Select-String -Path f:\power\numbers.txt -Pattern '^\d{3}-\d{3}-\d{4}'

```
