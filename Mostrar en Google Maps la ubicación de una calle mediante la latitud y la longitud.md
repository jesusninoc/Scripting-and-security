# Mostrar en Google Maps la ubicación de una calle mediante la latitud y la longitud
## PowerShell 
### URL: https://www.jesusninoc.com/2015/07/15/mostrar-en-google-maps-la-ubicacion-de-una-calle-mediante-la-latitud-y-la-longitud/
```PowerShell
#Utilizando The Google Geocoding API
#https://developers.google.com/maps/documentation/geocoding/

$calle='Avenida de Concha Espina 1'
$urlsi='https://maps.googleapis.com/maps/api/geocode/json?address=' + $calle + '+MADRID'
$urlsi=$urlsi.replace(' ','+')
$urlsi
$resulti=(Invoke-WebRequest -Uri $urlsi)

foreach($pit in $resulti.Content)
{
    $conver=$pit | ConvertFrom-JSON
    $lat=$conver.results.geometry.location.lat
    $long=$conver.results.geometry.location.lng
    $urlgooglemap='https://www.google.es/maps?q='+$lat+','+$long
    Start-Process chrome $urlgooglemap
}

```
