# Listar las empresas del IBEX 35 (versión optimizada)
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/02/21/listar-las-empresas-del-ibex-35-version-optimizada/
```PowerShell
(((Invoke-WebRequest 'http://www.bolsamadrid.es/esp/aspx/Mercados/Precios.aspx?indice=ESI100000000').AllElements).where{$_.Class -eq "DifFlBj" -or $_.Class -eq "DifFlSb" -or $_.Class -eq "DifFlIg"}).innerText

```
