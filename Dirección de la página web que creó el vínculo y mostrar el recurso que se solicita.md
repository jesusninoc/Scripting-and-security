# Dirección de la página web que creó el vínculo y mostrar el recurso que se solicita
## Logs, Security, Servers, Web 
### URL: https://www.jesusninoc.com/2009/05/04/direccion-de-la-pagina-web-que-creo-el-vinculo-y-mostrar-el-recurso-que-se-solicita/
```PowerShell
SELECT     Date, [c-ip], [cs(Referer)], [cs-uri-stem], [cs-uri-query]
FROM         tabla
WHERE     (Date > '2009-04-27')
ORDER BY [cs(Referer)] DESC

```
```PowerShell
30/04/2009 1:25:36 https://www.whois.sc/ /robots.txt -
28/04/2009 9:58:55 https://www.whois.sc/ /robots.txt -

```
