# Enviar un mensaje SMS en Android con ADB
## Android 
### URL: https://www.jesusninoc.com/2016/04/17/enviar-un-mensaje-sms-en-android-con-adb/
```PowerShell
adb shell am start -a android.intent.action.SENDTO -d sms:123456789 --es sms_body "Hi" --ez exit_on_sent true
adb shell input keyevent 22

```
