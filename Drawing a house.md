# Drawing a house
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2014/10/11/drawing-a-house/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$formGraphics = $form.createGraphics()

#Drawing tiled
$form.add_paint({$formGraphics.DrawLine($mypen, 100, 10, 10, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 100, 10, 200, 100)})

#Drawing square
#$form.add_paint({$formGraphics.DrawLine($mypen, 10, 10, 200, 10)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 100, 200, 100)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 200, 200, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 10, 100, 10, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 100, 200, 200)})

$form.ShowDialog()

```
