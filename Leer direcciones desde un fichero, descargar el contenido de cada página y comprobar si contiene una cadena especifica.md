# Leer direcciones desde un fichero, descargar el contenido de cada página y comprobar si contiene una cadena especifica
## Bash, Web 
### URL: https://www.jesusninoc.com/2016/02/09/leer-direcciones-desde-un-fichero-descargar-el-contenido-de-cada-pagina-y-comprobar-si-contiene-una-cadena-especifica/
```Shell
#Fichero urls contiene direcciones web, ejemplo:
#https://www.jesusninoc.com/
#https://www.jesusninoc.com/linux/

for url in `cat urls`
do
        echo $url
        ficherourl=`echo $url | sed 's/https://g' | sed 's/\///g'`
        wget -q --output-document $ficherourl $url
        cat $ficherourl | grep '<title>Scripting and security</title>'
done

```
