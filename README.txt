odysseusOTAPlus
Original: odysseusOTA2 by tihmstar: https://www.dropbox.com/s/c6rz5u2vw9oyf9f/odysseusOTA2-v1.0.4.zip

"""
WARNING: do not do it, unless you have read and understood these instructions.
If *anything* goes wrong during the restore process, you will have to restore
to the latest, most likely unjailbreakable firmware.  Basically, you are on
your own.  I will not be held responsible for anything YOU do.
"..."

Only devices that possible to execute pwnstrap by checkm8.
————————————————————————————————————————————————————————————————————————————————

This will change your baseband version!

You should really watch this video https://www.youtube.com/watch?v=Wo7mGdMcjxw [original] before trying to downgrade.

Commands:

#cd to the directory
cd odysseusOTA2Plus
cd macos *!!macos only!!

#build custom ipsw
./ipsw path_to_original_8.4.1_restore.ipsw custom_downgrade.ipsw -bbupdate
#DO NOT FORGET -bbupdate   !!!!!!

#download shsh blobs
./idevicerestore -t custom_downgrade.ipsw

#extract pwnediBSS
./xpwntool `unzip -j custom_downgrade.ipsw 'Firmware/dfu/iBSS*' | awk '/inflating/{print $2}'` pwnediBSS

#put the device in pwnedDFU mode
./pwnedDFU -p

#send file to device
./pwnedDFU -f pwnediBSS

#now back on the computer run the restore 
*You can restore to the latest baseband by using idevicererestore. (Recommended to prevent bugs caused by old BB)
./idevicererestore -r ./custom_downgrade.ipsw

Done :)

Credits:
@xerub for his odysseus tool
@planetbeing, dborca for the awesome xpwn
@winocm for ios-kexec-utils
@westbaer, p0sixninja, iH8sn0w, GreySyntax for irecovery
@libimobiledevice people for libimobiledevice
@iH8sn0w for some ideas and code
@daytonhasty for some ideas, testing and writeup
@JonathanSeals for some ideas
@citrusui for the cool name
@tihmstar for odysseusOTA2
@axi0mX for checkm8 exploit
@synackuk for pwneddfu shellcode

LICENSE: GPL-3.0

by dora2_yururi
