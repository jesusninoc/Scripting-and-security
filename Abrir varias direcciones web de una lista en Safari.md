# Abrir varias direcciones web de una lista en Safari
## AppleScript, Web 
### URL: https://www.jesusninoc.com/2016/02/01/abrir-varias-direcciones-web-de-una-lista-en-safari/
```AppleScript
set lista to {"https://www.jesusninoc.com","https://www.jesusninoc.com/applescript/"}
repeat with web in lista
tell application "Safari" to open location web
end repeat

```
