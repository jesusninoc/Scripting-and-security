# Bucles en PowerShell
## PowerShell 
### URL: https://www.jesusninoc.com/2015/09/29/bucles/
```PowerShell
#Mostrar los números del 1 al 10

#Bucle While
$i=1
while($i -lt 11){
$i
$i++
}

#Bucle Do-While
$i=1
do{
$i
$i++
}while($i -lt 11)

#Bucle For
for($i=1;$i -lt 11;$i++)
{
$i
}

#Bucle Foreach
foreach($i in 1..10)
{
$i
}

#Bucle Foreach abreviado
1..10 | % {$_}

```
