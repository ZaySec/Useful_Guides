
---
Windows 10/11
1. Open CMD with administrator
2. `diskpart` 
3. `list disk`
4. `select disk <Disk Number>`
>[!danger] *WARNING: `clean` DELETES ALL DATA* 
5. Wipe Drive
	1. `clean` 
	2. If `clean` doesn't work -> `convert gpt`)
6. `create partition primary`
7. Now format the USB
	1. Go to "**create and format hard disk partitions**" and right click partition to format
	- OR
	1. `format fs=<FAT32,exFAT, or NTFS> quick label="<name>"`
	2. `assign letter=<Letter>`
	3. `exit`
8. Done

---
# Linux
Main method:
1. `lsblk` : Find correct drive
2. `sudo ntfsfix /dev/sdb1` : Fix ntfs
	
Alternative method:
1. `lsblk` : Find the correct drive
2. `sudo dd if=/dev/zero of=/dev/<drive> bs=1M count=100` : dd to format
3. `d/<drive>`
	1. Which System?
		- Type `g` for GPT (UEFI systems / Reliable) 
		- OR Type `o` for MBR (Legacy)
	2. Type `n` for new partition (accept defaults)
		1. It will ask for how many partitions 
		2. Start sector
		3. End sector
	3. Type `w` to write changes
4. Make Filesystem (mkfs), in this case exfat
	- `sudo mkfs.exfat /dev/sdb`
5. Done

---
macOS
1. ?
---
Guides
 - https://www.how2shout.com/how-to/how-to-restore-a-bootable-usb-to-normal-complete-recovery-guide.html