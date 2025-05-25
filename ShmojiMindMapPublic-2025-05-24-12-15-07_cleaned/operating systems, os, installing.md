  * tracking thoughts
    * tracking learnings, experiences
      * [[2024-08-21]]
        * you cant just download ISO onto USB, plug it in, double click ISO file and it installs OS. You apparently have to use a tool to create a "bootable USB drive". This will write the ISO to the external device in way that makes it bootable
        * i used etcher after downloading ubuntu iso. You gotta download etcher app onto device, but it pretty quick. btw, the target is USB drive you want to make bootable
        * then you restart computer you want to apply os to and enter the BIOS/UEFI (prob F2, F10, F12 or delete during startup), Change the boot order to boot from USB drive and then save/exit bios. PS: i used UEFI option as first priority for boot (but p sure can use either with new computers)
        * well shoot, i learned you shouldnt use a big external hard drive for booting a new OS. Because after, youll likely need to reformat it to remove the bootable partition and reclaim the full space. So basically, after you make it a bootable device, it may be difficult to turn it back into a regular storage device again. Better to use USB
        * after making usb bootable, it automatically said i needed to format the usb to use it - this was windows - it's done and you dont have to do that