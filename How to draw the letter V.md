# How to draw the letter V
## Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2013/02/23/draw-letter-v/
```PowerShell
#Create pen
$mypen = new-object Drawing.Pen red
$mypen.width = 10

$form = New-Object Windows.Forms.Form
$form.Width = 500
$form.Height = 550
$formGraphics = $form.createGraphics()

#V
$form.add_paint({$formGraphics.DrawLine($mypen, 0, 0, 100, 200)})
$form.add_paint({$formGraphics.DrawLine($mypen, 200, 0, 100, 200)})

$form.ShowDialog()

```
