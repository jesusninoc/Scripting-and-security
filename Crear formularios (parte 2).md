# Crear formularios (parte 2)
## PowerShell 
### URL: https://www.jesusninoc.com/2016/02/25/crear-formularios-parte-2/
```PowerShell
#Crear un formulario, añadir una etiqueta y un botón
#Formulario
$Form=New-Object System.Windows.Forms.Form
$Form.Text="Formulario"
$Form.Size=New-Object System.Drawing.Size(500,500)
$Form.StartPosition="CenterScreen"

#Etiqueta
$Label=New-Object System.Windows.Forms.Label
$Label.Text="Etiqueta de ejemplo"
$Label.AutoSize=$True
$Label.Location=New-Object System.Drawing.Size(185,180)

#Botón
$Button=New-Object System.Windows.Forms.Button
$Button.Size=New-Object System.Drawing.Size(75,23)
$Button.Text="Botón"
$Button.Location=New-Object System.Drawing.Size(200,200)

#Añadir etiqueta
$Form.Controls.Add($Label)
#Añadir botón
$Form.Controls.Add($Button)

$Form.ShowDialog()

```
```PowerShell
#Crear un formulario, añadir una etiqueta, un botón y una caja de texto
#Formulario
$Form = New-Object System.Windows.Forms.Form
$Form.Text="Formulario"
$Form.Size=New-Object System.Drawing.Size(500,500)
$Form.StartPosition="CenterScreen"

#Etiqueta
$Label=New-Object System.Windows.Forms.Label
$Label.Text="Etiqueta de ejemplo"
$Label.AutoSize=$True
$Label.Location=New-Object System.Drawing.Size(180,160)

#Botón
$Button=New-Object System.Windows.Forms.Button
$Button.Size=New-Object System.Drawing.Size(75,23)
$Button.Text="Botón"
$Button.Location=New-Object System.Drawing.Size(195,180)

#Caja de texto
$TextBox = New-Object System.Windows.Forms.TextBox
$TextBox.Location = New-Object System.Drawing.Size(110,215)
$TextBox.Size = New-Object System.Drawing.Size(260,20)

#Añadir etiqueta
$Form.Controls.Add($Label)

#Añadir botón
$Form.Controls.Add($Button)

#Añadir caja de texto
$Form.Controls.Add($TextBox)

$Form.ShowDialog()

```
