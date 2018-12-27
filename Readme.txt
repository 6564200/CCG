StartUP CasparCG Server:

Edit config visudo
> sudo visudo
+ Cmnd_Alias      CCGS=/home/casparcg/CasparCG_Server/bin/casparcg, /home/casparcg/CasparCG_Server/run
+ casparcg        ALL=NOPASSWD:   CCGS

create and compil server.c
> nano server.c

+ #include <stdio.h>
+ #include <stdlib.h>
+ #include <unistd.h>
+ int main() { sleep(20); system ("gnome-terminal -x sudo /home/casparcg/CasparCG_Server/run"); return 0;}

> gcc -Wall -o server server.c
> sudo chown root server
> sudo chmod u+s server

Copy file to /bin

Install StartUp Aplication and add /bin/server

System without monitor attached:

generate config monitor edid.conf NVIDIA Util 
copy /etc/X11/edid.conf
edit /etc/X11/xorg.conf
Section "Device"
    Identifier     "Device0"
    Driver         "nvidia"
    VendorName     "NVIDIA Corporation"
    BoardName      "GeForce blabla
    Option "ConnectedMonitor" "CRT-0"
    Option "CustomEDID" "CRT-0:/etc/X11/edid.conf"
EndSection
