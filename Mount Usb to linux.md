
1. Download fuse and ntfs-3g
2. sudo fdisk -l (make sure the usb is connected)
3. sudo mkdir /mnt/media
4. add, "'UUID' /mnt/media ntfs-3g defaults, 0 0" to /etc/fstab and to find UUID use "sudo blkid"
5. reboot to get working!

---
1. Create a mountpoint 
	- Skip if you have a mount point
	- `sudo mkdir -p /mnt/mount_1`
2. Mount device (`/dev/sdb1`) to a directory (`/mnt/mount_1`)
	- Note: If you have `exFAT` you need `fuse` 
		- `sudo pacman -S fuse`
	- `sudo mount /dev/sdb1 /mnt/mount_1` 