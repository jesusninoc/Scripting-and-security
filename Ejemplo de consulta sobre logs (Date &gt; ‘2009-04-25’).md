# Ejemplo de consulta sobre logs (Date &gt; ‘2009-04-25’)
## Logs, Security, Servers 
### URL: https://www.jesusninoc.com/2009/05/04/ejemplo-de-consulta-sobre-logs-date-2009-04-25/
```PowerShell
SELECT     Date, [cs(Referer)], [cs-uri-stem], [cs-uri-query]
FROM         tabla
WHERE     (Date > '2009-04-25')
ORDER BY Date

```
