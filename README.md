# yocto-mini2440

This is a project for mini2440 in general, with a target to create a yocto project in the end.

If you have an old mini2440, accidentally load an uboot, and tried boot from nfs, but those nfs story lost, board won't boot any more.
It is frustrating when mini2440 looks like this.
So I decided to load uboot, kernel, file system back to mini2440's onboard NAND.

uboot? nah, mini2440 didn't talk about uboot, they talk about supervivi. anyway as long as Linux boots.

Ok supervivi, but how, read the user manual, choose option [v]

but how to upload supervivi to mini2440 from Ubuntu, if you have an old PC with Windows PC, use dnw.exe.
But Ubuntu do this:
  git clone https://github.com/ClubINTech/mini2440-startup-guide.git
  download s3c2410_boot_usb source code and build your own.
  make
  Compile errors??
  sudo apt-get install libusb-dev
  make
  Errors again?
  Try build with gcc -o xx xx.c -lusb
  put lusb at the end.
  You will see my make file in this project.
 
 Now build s3c2410_boot_usb ready!!
 ./s3c2410_boot_usb supervivi-128M
 
 Now kernel, [k]
 sudo ./s3c2410_boot_usb zImage_W35
 Now file system [y]
 sudo ./s3c2410_boot_usb rootfs_qtopia_qt4.img
 
 Power off and power on, now mini2440 boot Linux straight away.
 
 
  
  
