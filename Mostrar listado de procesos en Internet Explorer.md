# Mostrar listado de procesos en Internet Explorer
## PowerShell 
### URL: https://www.jesusninoc.com/2016/03/24/mostrar-listado-de-procesos-en-internet-explorer/
```PowerShell
$oIE=new-object -com internetexplorer.application
$oIE.navigate2("About:blank")
while ($oIE.busy) {
    sleep -milliseconds 50
}
$oIE.visible=$true

$procesos=(ps).name | %{$_}

$params=[String]"<html><body>"+$procesos+"</body></html>"

$oIE.document.write($params)

```
