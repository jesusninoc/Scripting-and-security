# Convertir un texto en un fichero WAV
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2016/04/11/convertir-un-texto-en-un-fichero-wav/
```PowerShell
[void][reflection.assembly]::loadwithpartialname(‘system.speech’)
$speech = New-Object System.Speech.Synthesis.SpeechSynthesizer
$saludo= "hola, hola"
#$cierre="adiós, adiós"
$speech.SetOutputToWaveFile("d:\holas.wav")
$speech.Speak($saludo)
$speech.SetOutputToDefaultAudioDevice()

```
