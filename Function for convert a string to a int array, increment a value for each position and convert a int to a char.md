# Function for convert a string to a int array, increment a value for each position and convert a int to a char
## Cryptography, PowerShell, Security, Strings 
### URL: https://www.jesusninoc.com/2014/03/10/function-for-convert-a-string-to-a-int-array-increment-a-value-for-each-position-and-convert-a-int-to-a-char/
```PowerShell
#Function
function cif($a)
{
for($c=0; $c -lt $a.Length; $c=$c+1)
{[char]([int]$a[$c]+1)}
}

#Call
[string]$a="PowerShell"
$b=cif($a)
$b

```
