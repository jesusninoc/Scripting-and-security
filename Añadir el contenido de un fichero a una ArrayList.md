# Añadir el contenido de un fichero a una ArrayList
## PowerShell 
### URL: https://www.jesusninoc.com/2015/08/28/anadir-el-contenido-de-un-fichero-a-una-arraylist/
```PowerShell
$fichero = Get-Content C:\Users\lam\Desktop\fichero.txt

#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList

ForEach ($elemento in $fichero){
#Agrega un objeto al final de ArrayList
[void]$arraylist.Add($elemento)
}

#Número de elementos de ArrayList
$arraylist.Count

```
