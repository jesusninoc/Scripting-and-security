# Devolver una cadena que representa el intervalo calculado que contiene un número
## PowerShell, Visual Basic 
### URL: https://www.jesusninoc.com/2016/02/17/devolver-una-cadena-que-representa-el-intervalo-calculado-que-contiene-un-numero/
```PowerShell
#https://msdn.microsoft.com/es-es/library/microsoft.visualbasic.interaction.partition(v=vs.110).aspx

#Public Shared Function Partition (
# Number As Long,
# Start As Long,
# Stop As Long,
# Interval As Long
#) As String

Add-Type -AssemblyName Microsoft.VisualBasic

$year=1984
[Microsoft.VisualBasic.Interaction]::Partition($year, 1950, 2049, 10)

```
