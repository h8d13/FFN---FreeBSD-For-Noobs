# OS-Deep
Deep dive into Operating Systems. I think I'm reaching the end of the rabbit hole... Or am I?

## Split 1

- Windows 
- Linux
- MaccOS
- OPENBSD / FREEBSD

### Predecessors

- DOS
- Unix

----- 

## Distributions

We talk of ditributions but each distro has it's own releases types:
Often broken down into: 

Architecture Type & Installation type

Architectures > Processors
```
amd64
i386
aarch64
armv7
powerpc
powerpc64
powerpc64le
powerpcspe
riscv64

Might also include specific, Netboot Images, VM Images, SD Card Images, etc
``` 

While the installation type is often the contents itself: `Minimal, server, desktop, live environment, ...` 
Hence why it's important to go some do some research for the type of project you are aiming to achieve. 


Hint :
> Look at the sizes of the installers they can be a good indication.
> For example alpine is 5mb, alpine with base utils is going to be more... You get the idea.

This installer size is illustrative and will take more space on disk (after unpacking), unless it's a live system.

-----

For most OSes you will have to go through some basic documentation to get started.

But here we love to fail and brick the install 50 times so let's proceed. 
![Screenshot from 2025-03-25 22-28-09](https://github.com/user-attachments/assets/93d93e2e-1da1-41f0-b1df-99695db8b9e1)

--- 

Step 1. Get through installers, on some systems it's hell. Here it's actually not that bad. 
We can use arrows space and enter for base config of what we want. 

What we can do in the meantime is make sure we know what we have to do next. 

First we'll need to update our sources like on other operation systems.

pkg update && pkg upgrade
freebsd-update fetch 
freebsd-update install 

-----


Let it rip for a bit. Some lines will execute for longer that is normal. 

pkg install gnome-desktop gdm xorg
Enable the required services in /etc/rc.conf:

echo 'gnome_enable="YES"' >> /etc/rc.conf
Do the same for gdm and dbus.

-----

BIOSes 

- SEABIOS
- OpenFirmware
- Much garbage here.


-----

Okay lesson 1. ALways create a user when prompted. Even if that no button is tempting. 

