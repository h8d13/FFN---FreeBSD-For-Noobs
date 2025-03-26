# FreeBSD 

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
I picked the DVD as I believe it comes with most pre-installed. 

-----

For most OSes you will have to go through some basic documentation to get started.

But here we love to fail and brick the install 50 times so let's proceed. 
![Screenshot from 2025-03-25 22-28-09](https://github.com/user-attachments/assets/93d93e2e-1da1-41f0-b1df-99695db8b9e1)

--- 

Step 1. Get through installers, on some systems it's hell. Here it's actually not that bad. 
We can use arrows, space to select and enter for base config of what we want. 

I ticked all but the "dbg" packages as I guess they are verbose vversions I did not need. 

What we can do in the meantime is make sure we know what we have to do next. 

First we'll need to update our sources like on other operation systems.
```
pkg update && pkg upgrade
```
Then:

`pkg install -y kde5 xorg sddm` 

Little trick: if you want KDE without all the pre-installed apps: use plasma5-plasma instead. This will reduce the downloads by 30%-50%. 

Then go to the user and run `startx` this is the manual way (that I enjoy.)

Or you can add it to a file in the home directory of the user in ~/.xinitrc 
`exec startplasma-x11`

Okay lesson 1. Always create a user when prompted. Even if that no button is tempting. 

-----

![Screenshot from 2025-03-25 23-58-39](https://github.com/user-attachments/assets/5c42851c-de1c-4153-87eb-6d61ac50b409)

Now don't forget to:

```
freebsd-update fetch
```
then the same but install. 

----

As alwyas to fix my keyboard in login manager. 

Add `setxkbmap fr` in `/usr/local/share/sddm/scripts/Xsetup` and reboot. 

---

Overall this was one of the simplest and most well guided installers I've come accross. It is intuitive yet customizable. Also love the security options put forward. 

Total installation size minimal KDE was about 4.56Gib vs 7.5Gib for the full with games and utilities. 



