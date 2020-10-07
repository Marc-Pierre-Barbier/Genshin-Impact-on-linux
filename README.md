# Genshin-Impact-on-linux
*this isn't the best experience and you will get artifacts on the screen but still work.
i recomend to use vfio/gpu passthrough
*gvt-g will give you a terrivle experience and qemu desn't have good virtual gpus for windows
*virtualbox 3d only has 256GB i don't expect good performance of it
*the anticheat doesn't run in wine

wich leaves us with 2 option ONLY CHOSE ONE :
1. pcie passthrough (you can find tutorials on the vfio page of the arch wiki)
2. vmware 3d gpu (this tutorial)
## installing vmware
on arch there is performance issue with vmware from aur (as reported by Xaero)
so try to avoid it go and get it on the webside and follow the install instruction on the archwiki

on systemd based system :
follow the instruction and manualy add the services listed
https://wiki.archlinux.org/index.php/VMware#Installation

on init.d based the whole processe should be strait-forward just download the .bundle and run it

## get a windows iso
DO NOT USE WINDOWS LIGHT OR ANY MODIFED WINDOWS (tuxkamen on discord and u/Dazzling-Princess had this issue)
you can get one for free on the microsoft website.

## setting up the vm
* create a virtual machine and set it's ram amount to anything >= 8GB
* set the gpu vram to 2GB (work around some visual glitches Xaero still experienced issues event after the fix)
* install windows
* (this might not be needed)in windows you need to unsintall vmware tools before installing this version of vmware tools 
https://packages.vmware.com/tools/releases/latest/windows/x64/VMware-tools-11.1.5-16724464-x86_64.exe
* then shut down the vm
* go into the virualmachine settings -> options -> advanced and copy the path to the vmx
* edit the vmx file and append at then end ```hypervisor.cpuid.v0 = "FALSE"``` this will mask the virtualmachine since the game won't start without
* save and start the vm
* install the game
* go into the game launcher folder and run the setup inside the DXSETUP folder this will fix the white screen bug
* launche the game and change the screen resolution i had 4k by default (this will cause the game to display in windowed you might try https://github.com/Codeusa/Borderless-Gaming/releases)
* play the game

## problems
 * extremly bright artifact all around the caste in the begining of the game and in the borders of the skybox the cause is unkown
 * black bushes until you get close enough (might be a lod issue) 

# Credits

all this work was made with the help of the folks on the lutris discord
and special thanks to Xaero wich helped me greatly

the white screen workaround comes from (https://www.ghostarrow.com/genshin-impact-wont-launch-how-to-fix)
