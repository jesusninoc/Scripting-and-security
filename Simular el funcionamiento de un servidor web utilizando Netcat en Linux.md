# Simular el funcionamiento de un servidor web utilizando Netcat en Linux
## Bash, Web 
### URL: https://www.jesusninoc.com/2016/04/30/simular-el-funcionamiento-de-un-servidor-web-utilizando-netcat-en-linux/
```Shell
echo '<html><title>hola</title></html>' | nc -l -p 99 -q 1

```
```Shell
wget https://localhost:99

```
