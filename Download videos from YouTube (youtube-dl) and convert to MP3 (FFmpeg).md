# Download videos from YouTube (youtube-dl) and convert to MP3 (FFmpeg)
## Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2014/10/19/download-videos-youtube-youtube-dl-convert-mp3-ffmpeg/
```PowerShell
#Open file
(Get-Content F:\power\urls.txt) | %{
#URL
Write-Host $_
#Save file in c:\power
Set-Location F:\power
#Use youtube-dl to download video from Youtube
#Youtube-dl is a small command-line program to download videos from YouTube.com and a few more sites.
F:\power\youtube-dl.exe $_ > result.txt
#Select file in result.txt
$result=(Get-Content result.txt)
$file=$result -match 'Destination: '
$file=$file.Replace('[download] Destination: ','')
$filewithoutspaces=$file.Replace(' ','')
$filewithoutext=$filewithoutspaces.replace('.mp4','.mp3')
#Rename file and replace spaces
Rename-Item $file $filewithoutspaces
#Convert MP4 to MP3 with FFmpeg
#FFmpeg complete, cross-platform solution to record, convert and stream audio and video.
#Example ffmpeg -i input.mp4 output.mp3
F:\power\ffmpeg\bin\ffmpeg.exe -i $filewithoutspaces -acodec libmp3lame -ab 128k $filewithoutext
}

```
