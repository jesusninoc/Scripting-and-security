# Convert a string to a int array and increment a value for each position
## PowerShell, Strings 
### URL: https://www.jesusninoc.com/2014/03/10/convert-a-string-to-a-int-array-and-increment-a-value-for-each-position/
```PowerShell
[string]$a="PowerShell"
for($i=0; $i -lt $a.Length; $i=$i+1)
{[char]([int]$a[$i]+1)}

```
