# Realizar una búsqueda con Google Chrome en Android mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/03/26/realizar-una-busqueda-con-google-chrome-en-android-mediante-adb-a-traves-de-powershell/
```PowerShell
#Abrir Google Chrome en Android mediante ADB
#Es necesario habilitar el modo depuración en Android
cd "D:\program\android-sdk-windows\platform-tools"
.\adb shell am start -n com.android.chrome/com.google.android.apps.chrome.Main -d 'https://www.google.es'
Start-Sleep -Seconds 5
.\adb shell input tap 101 880
.\adb shell input text "powershell"
.\adb shell input keyevent 66

```
