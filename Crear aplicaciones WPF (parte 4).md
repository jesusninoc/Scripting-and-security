# Crear aplicaciones WPF (parte 4)
## PowerShell 
### URL: https://www.jesusninoc.com/2016/09/11/crear-aplicaciones-wpf-parte-4/
```PowerShell
Add-Type -AssemblyName PresentationFramework
  
$codigoxaml = @'
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="My First WPF Application" Height="350" Width="525">
    <Grid>
        <Viewbox>
            <TextBlock Text="Hello World!"
                       HorizontalAlignment="Center"
                       VerticalAlignment="Center"
                       FontSize="50"
                       RenderTransformOrigin="0.5,0.5"
                       FontWeight="Bold">
            </TextBlock>
        </Viewbox>
    </Grid>
</Window>
'@

$cargar = [System.XML.XMLReader]::Create([System.IO.StringReader]$codigoxaml)
$ventana = [System.Windows.Markup.XAMLReader]::Load($cargar)
$ventana.ShowDialog()

```
