# Pulsar sobre un enlace en el navegador desde Python
## Python 
### URL: https://www.jesusninoc.com/2016/05/01/pulsar-sobre-un-enlace-en-el-navegador-desde-python/
```Python
from selenium import webdriver
browser = webdriver.Firefox()
browser.get('https://www.jesusninoc.com')
linkElem = browser.find_element_by_link_text('Python')
linkElem.click()

```
