# Planet order list
## PowerShell, Web scraping 
### URL: https://www.jesusninoc.com/2016/04/04/planet-order-list/
```PowerShell
((Invoke-WebRequest 'https://cse.ssl.berkeley.edu/AtHomeAstronomy/act09_planet_list.html').AllElements | Where-Object width -EQ "47%").innerText

```
