# Reproducir frecuencias con rtl_fm
## Bash, Multimedia, Radio 
### URL: https://www.jesusninoc.com/2016/04/20/reproducir-frecuencias-con-rtl_fm/
```Shell
rtl_fm -f 434977400 -M fm -s 170k -A fast -r 32k -l 0 -E deemp | play -r 32k -t raw -e s -b 16 -c 1 -V1 -

```
