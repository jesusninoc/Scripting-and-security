# Simular el pulsado de números en Android mediante ADB a través de PowerShell
## Android, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/17/simular-el-pulsado-de-numeros-en-android-mediante-adb-a-traves-de-powershell/
```PowerShell
Set-Location "C:\Program Files (x86)\Android\android-sdk\platform-tools"
.\adb shell input keyevent KEYCODE_9
.\adb shell input keyevent KEYCODE_8
.\adb shell input keyevent KEYCODE_7

```
