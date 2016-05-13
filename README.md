# image-builder
Various scripts that you can chain together to create debian installations for various devices.

It was originally intended for the pogoplug v4

## usage
[varibles] script [vars|check|start]
script vars will print every variable that the script accepts
script check will print every variable that the script accepts, and what was passed to them.  You can use this to check for anything you left out
script start will execute the script

## examples
DRIVE "/dev/sda" is the drive to partition
BOOT "/dev/sda1" is the boot partition to format, mount, add to fstab
ROOT "/dev/sda2" is the root partition to format, mount, add to fstab, pass to initramfs on boot
TARGET "/target" is the location that all operations are performed on. mount, debootstrap, chroot 


DRIVE="/dev/sda" BOOT="/dev/sda1" ROOT="/dev/sda2" TARGET="/target" ./65rootsshkey.sh check
DRIVE="/dev/sda" BOOT="/dev/sda1" ROOT="/dev/sda2" TARGET="/target" ./65rootsshkey.sh start


DRIVE="/dev/sda" BOOT="/dev/sda1" ROOT="/dev/sda2" TARGET="/target" run-parts -a check .
DRIVE="/dev/sda" BOOT="/dev/sda1" ROOT="/dev/sda2" TARGET="/target" run-parts -a start .
