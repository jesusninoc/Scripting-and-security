# Download videos from YouTube, convert MP4 to JPEG and convert JPEG to HTML
## Graphics, Multimedia, PowerShell 
### URL: https://www.jesusninoc.com/2014/11/07/download-videos-from-youtube-convert-mp4-to-jpeg-and-convert-jpeg-to-html/
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
#Extract images
#FFmpeg complete, cross-platform solution to record, convert and stream audio and video.
#Example ffmpeg.exe -i $filewithoutspaces -r 1 -s 4cif -f image2 $jpg-%3d.jpeg
#4cif options stands for the frame size 704x576. There are a variety of options that you can use.
#
#sqcif 128x96 qcif 176x144 cif 352x288
#4cif 704x576 qqvga 160x120 qvga 320x240
#vga 640x480 svga 800x600 xga 1024x768
#uxga 1600x1200 qxga 2048x1536 sxga 1280x1024
#qsxga 2560x2048 hsxga 5120x4096 wvga 852x480
#wxga 1366x768 wsxga 1600x1024 wuxga 1920x1200
#woxga 2560x1600 wqsxga 3200x2048 wquxga 3840x2400
#whsxga 6400x4096 whuxga 7680x4800 cga 320x200
#hd480 852x480 hd720 1280x720 hd1080 1920x1080
mkdir $filewithoutext
$jpg='$filewithoutext\imagen'
F:\power\ffmpeg\bin\ffmpeg.exe -i $filewithoutspaces -r 1 -s sqcif -f image2 $jpg-%3d.jpeg
foreach ($im in (ls $filewithoutext)){
#Call function convert JPEG to HTML
convert $im.FullName
}
}

#Function convert JPEG to HTML
function convert{
Param($im)
$im
$Cave = [System.Drawing.Bitmap]::FromFile($im)
$i=0
$uu=''
for ($x = 0;$x -lt $Cave.Height;$x+=1)
{
for ($y = 0;$y -lt $Cave.Width;$y+=1)
{
if ($i -lt $Cave.Width -1)
{
$com='<font size=''2'' color=''' + ($Cave.GetPixel($y,$x).name).substring(2,6) + '''>█</font>'
$uu=$uu+$com
$i=$i+1
}
else
{
$uu=$uu+ '<br>'
$i=0
$a=0
}
}
}
$uu | Out-File $im.replace('.jpeg','.html') -Append
}

```
