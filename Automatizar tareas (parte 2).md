# Automatizar tareas (parte 2)
## Automation, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/28/automatizar-tareas-parte-2/
```PowerShell
#Leer operaciones desde un fichero

#Ejemplo de contenido
#Mover el ratón y hacer clic en distintas posiciones

#Guardar el siguiente contenido sin el carácter # en un fichero llamado acciones.txt
#clic,442,386
#clic,452,386
#clic,462,386
#clic,472,386
#clic,482,386

#Importante:
#Sustituir las comillas

$MouseEventSig=@'
[DllImport("user32.dll",CharSet=CharSet.Auto, CallingConvention=CallingConvention.StdCall)]
public static extern void mouse_event(long dwFlags, long dx, long dy, long cButtons, long dwExtraInfo);
'@

Get-Content F:\power\acciones.txt | %{

$MouseEvent = Add-Type -memberDefinition $MouseEventSig -name "MouseEventWinApi" -passThru

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
'clic'{
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point($param1,$param2)
$MouseEvent::mouse_event(0x00000002, 0, 0, 0, 0)
$MouseEvent::mouse_event(0x00000004, 0, 0, 0, 0)
break
}
}
Start-Sleep -Seconds 5
}

```
