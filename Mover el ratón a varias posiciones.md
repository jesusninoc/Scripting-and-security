# Mover el ratón a varias posiciones
## Automation, Graphics, PowerShell 
### URL: https://www.jesusninoc.com/2015/01/18/mover-el-raton-a-varias-posiciones/
```PowerShell
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(100,100)
Start-Sleep -Milliseconds 50
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(200,200)
Start-Sleep -Milliseconds 50
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(300,300)
Start-Sleep -Milliseconds 50
[System.Windows.Forms.Cursor]::Position = New-Object System.Drawing.Point(400,400)

```
