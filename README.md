# Genshin-Impact-on-linux

## installing vmware
on arch there is performance issue with vmware from aur (as reported by Xaero)
so try to avoid it go and get it on the webside and follow the install instruction on the archwiki

on systemd based system :
follow the instruction and manualy add the services listed
https://wiki.archlinux.org/index.php/VMware#Installation

on init.d based the whole processe should be strait-forward just download the .bundle and run it

## setting up the vm
* create a virtual machine and set it's ram amount to anything >= 8GB
* set the gpu vram to 2GB (work around visual glitches Xaero still experienced issues event after the fix)
* install windows
* (this might not be needed)in windows you need to unsintall vmware tools before installing this version of vmware tools 
https://packages.vmware.com/tools/releases/latest/windows/x64/VMware-tools-11.1.5-16724464-x86_64.exe
* then shut down the vm
* go into the virualmachine settings -> options -> advanced and copy the path to the vmx
* edit the vmx file and append at then end ```hypervisor.cpuid.v0 = "FALSE"``` this will mask the virtualmachine since the game won't start without
* save and start the vm
* install the game
* go into the game launcher folder and run the setup inside the DXSETUP folder this will fix the white screen bug
* play the game

# Credits

all this work was made with the help of the folks on the lutris discord
and special thanks to Xaero wich helped me greatly

the white screen workaround comes from (https://www.ghostarrow.com/genshin-impact-wont-launch-how-to-fix)
