# Añadir los nombres de los procesos a una ArrayList y buscar un elemento
## PowerShell 
### URL: https://www.jesusninoc.com/2016/09/16/anadir-los-nombres-de-los-procesos-a-una-arraylist-y-buscar-un-elemento/
```PowerShell
#Inicializa una nueva instancia de la clase ArrayList que está vacía y tiene la capacidad inicial predeterminada
[System.Collections.ArrayList] $arraylist = New-Object System.Collections.ArrayList
 
ForEach ($elemento in (ps | Group-Object Name).Name){
#Agrega un objeto al final de ArrayList
[void]$arraylist.Add($elemento)
}

if($arraylist.IndexOf("chrome") -eq -1)
{
"Elemento no encontrado"
}
else
{
'Elemento encontrado en la posición ' + $arraylist.IndexOf("chrome")
}

```
