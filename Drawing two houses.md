# Drawing two houses
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/10/11/drawing-two-houses/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#House 1
$form.add_paint({$formGraphics.DrawLine($mypen, 100, 10, 10, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 100, 10, 200, 100)})

$form.add_paint({$formGraphics.DrawLine($mypen, 10, 100, 200, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 200, 200, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 100, 10, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 100, 200, 200)})

#House 2
$form.add_paint({$formGraphics.DrawLine($mypen, 300, 10, 210, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 300, 10, 400, 100)})

$form.add_paint({$formGraphics.DrawLine($mypen, 210, 100, 400, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 210, 200, 400, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 210, 100, 210, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 400, 100, 400, 200)})

$form.ShowDialog()

```
