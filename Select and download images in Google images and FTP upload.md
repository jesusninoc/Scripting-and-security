# Select and download images in Google images and FTP upload
## PowerShell, Servers 
### URL: https://www.jesusninoc.com/2014/04/13/select-and-download-images-in-google-images-and-ftp-upload/
```PowerShell
$i=1
(Invoke-WebRequest “https://www.google.es/search?q=powershell&tbm=isch” | select -expand images | select -expand src) |
%{
$name="imagen"+$i+".jpg"
Start-BitsTransfer -Source $_ -Destination c:\powershell\$name
$i++

$file="c:\powershell\$name"
$ftp="ftp://user:pass@domain.com/pub/$i.zip"

$webclient = New-Object System.Net.WebClient
$uri = New-Object System.Uri($ftp)

$webclient.UploadFile($uri, $file)
}

```
