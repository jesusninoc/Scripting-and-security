# Automatizar tareas (parte 1)
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/27/automatizar-tareas-parte-1/
```PowerShell
#Leer operaciones desde un fichero

#Ejemplo de contenido
#Abrir Notepad, escribir un texto y cerrar el fichero sin guardar

#Guardar el siguiente contenido sin el carácter # en un fichero llamado acciones.txt
#abrir,notepad,0
#escribir,jesusninoc,0
#escribir,{ENTER},0
#escribir,%{F4},0
#escribir,%{n},0

Get-Content F:\power\acciones.txt | %{

$operacion=$_.split(',')[0]
$param1=$_.split(',')[1]
$param2=$_.split(',')[2]

switch($operacion){
'abrir'{
Start-Process $param1
Start-Sleep -Seconds 5
break
}
'escribir'{
[System.Windows.Forms.SendKeys]::SendWait($param1)
break
}
}
Start-Sleep -Seconds 5
}

```
