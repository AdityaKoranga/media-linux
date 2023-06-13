# media-linux
For external hardware connected to the server:

1. Identify the hard drive: Use `lsblk` or `fdisk -l` command to list all block devices, your newly attached drive should appear here.

![image](https://github.com/AdityaKoranga/media-linux/assets/95766110/aa243267-4516-4683-b18c-d021b9f1346c)
In my case it is sdc1


3.  Create a mount point:
sudo mkdir /media/new_drive
```bash
sudo mkdir /media/oran
```
3. Mount the drive 
```bash
sudo mount /dev/sdc1 /media/oran
```
> After completing all the things unmount the drive before removing it:
```bash
sudo umount /media/oran
```

Now you can see all the files of hard-drive
4. Automatic Mounting for next time:

* UUID of the hard drive.
```bash
sudo blkid
```
![image](https://github.com/AdityaKoranga/media-linux/assets/95766110/26cb0356-c84d-40ed-8e84-575a35f84061)

* Edit `/etc/fstab` file and add the line `UUID=your-uuid /media/new_drive ext4 defaults 0 2` like this:

```bash
vim /etc/fstab
```
add the line:
```bash
UUID=6b3a4878-545a-4595-8c41-ec5f02e9ab8d /media/oran ext4 defaults 0 2
```
Everything's set now!
