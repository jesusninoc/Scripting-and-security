# Listar las empresas del IBEX 35
## PowerShell, Web, Web scraping 
### URL: https://www.jesusninoc.com/2015/12/30/listar-las-empresas-del-ibex-35/
```PowerShell
$web=Invoke-WebRequest 'http://www.bolsamadrid.es/esp/aspx/Mercados/Precios.aspx?indice=ESI100000000'
$web.AllElements | Where Class -eq “DifFlBj” | %{$_.innerText}
$web.AllElements | Where Class -eq “DifFlSb” | %{$_.innerText}
$web.AllElements | Where Class -eq “DifFlIg” | %{$_.innerText}

```
