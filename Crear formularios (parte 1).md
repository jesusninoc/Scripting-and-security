# Crear formularios (parte 1)
## PowerShell 
### URL: https://www.jesusninoc.com/2014/11/09/crear-formularios-parte-1/
```PowerShell
#Crear un formulario
$Form = New-Object System.Windows.Forms.Form
#Form.ShowDialog (Método)
#Muestra el formulario como un cuadro de diálogo modal
$Form.ShowDialog()

```
```PowerShell
#Añadir un título a un formulario
$Form = New-Object System.Windows.Forms.Form
#Control.Text (Propiedad)
#Obtiene o establece el texto asociado al control
$Form.Text = "Nuevo formulario"
$Form.ShowDialog()

```
```PowerShell
#Añadir una etiqueta a un formulario
$Form = New-Object System.Windows.Forms.Form
$Label = New-Object System.Windows.Forms.Label
$Label.Text = "Etiqueta de ejemplo"
#Label.AutoSize (Propiedad)
#Obtiene o establece un valor que indica si el control cambia automáticamente de tamaño para mostrar todo su contenido
$Label.AutoSize = $True
#Control.ControlCollection.Add (Método)
#Agrega el control especificado a la colección del control.
$Form.Controls.Add($Label)
$Form.ShowDialog()

```
```PowerShell
#Añadir una etiqueta a un formulario con un estilo de fuente: Times New Roman tamaño 18 y ajustando el tamaño del formulario para poder ver correctamente la etiqueta
$Form = New-Object System.Windows.Forms.Form
#Font (Clase)
#Define un formato concreto para el texto, incluidos el nombre de fuente, el tamaño y los atributos de estilo. Esta clase no puede heredarse
$Font = New-Object System.Drawing.Font("Times New Roman",18,[System.Drawing.FontStyle]::Italic)
#Control.Font (Propiedad)
#Obtiene o establece la fuente del texto que muestra el control.
$Form.Font = $Font
$Label = New-Object System.Windows.Forms.Label
$Label.Text = "Etiqueta de ejemplo"
$Label.AutoSize = $True
$Form.Controls.Add($Label)
#Form.AutoScroll (Propiedad)
#Obtiene o establece un valor que indica si en el formulario se permite el desplazamiento automático
$Form.AutoScroll = $True
#Form.AutoSize (Propiedad)
#Cambie el tamaño del formulario de acuerdo con la configuración de AutoSizeMode
$Form.AutoSize = $True
#Form.AutoSizeMode (Propiedad)
#Obtiene o establece el modo por el que el formulario cambia automáticamente de tamaño
$Form.AutoSizeMode = "GrowAndShrink"
$Form.ShowDialog()

```
