
## `Linux CLI`
1. Wipe it : `sudo wipefs -a /dev/sdX`
2. Format to fat32 : `sudo mkfs.fat -F 32 /dev/sdX`
3. Mount device : `sudo mount /dev/sdb /mnt/usb`
4. Copy BIOS update to directory : `sudo cp ~/File_Location/BIOSFILE /mnt/usb1/`
5. Eject : `sudo umount /mnt/usb1`

---
Part 2: Turning the USB back to normal

1. Wipe drive : `sudo wipefs -a /dev/sdb`
2. Make label : `sudo parted /dev/sdb --script mklabel msdos`
3. Make a partition : `sudo parted /dev/sdb --script mkpart primary fat32 1MiB 100%`
4. Remake the USB : `sudo mkfs.fat -F 32 /dev/sdb1`