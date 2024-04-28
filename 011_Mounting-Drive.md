# Connecting & Mounting External Drive:

Below are instructions for connecting your external SSD. Or you can follow the instructions for attaching an external drive found at:

https://stadicus.github.io/RaspiBolt/raspibolt_20_pi.html 

in the Raspberry Pi section under Attach External Drive:

`$sudo dmesg -C;`

`$sudo dmesg -w;`

Now connect your external drive.

Make note of idVendor & idProduct. For example: idVendor = 1058 & idProduct = 0748

`$ctl+c;`

`$lsblk -o NAME,MOUNTPOINT,UUID,FSTYPE,SIZE,LABEL,MODEL;`

Make note of the partition name. For example: sda or sda1.

Test your external drive's performance with:

`$sudo hdparm -t --direct /dev/XXX;`

(Where XXX = your partition name).

You should get a result that reads something like: Timing O_DIRECT disk reads: 200 MB in 3.0 seconds = 66.66 MB/s.

If your results are less than 50 MB/s then follow the next step with your idvendor & idproduct from above. Otherwise, skip ahead to "$sudo mkfs.ext4...".

First edit the cmdline text file:

`$sudo nano /boot/cmdline.txt;`

At the very beginning of the text in the file insert:

`usb-storage.quirks=XXXX:YYYY:u`

Where XXXX=idVendor & YYYY=idProduct. Make sure you leave a single space after the "u" and before the original text.

Save the text file by hitting ctrl+x, y for yes, and enter.

`$sudo reboot;`

Once you're all logged back in and back in the shell, re-run the performance test.

`$sudo hdparm -t --direct /dev/sda1;`

You should have increased performance. If not, get a new external drive and start again.

Format the partition on the external drive.

`$sudo mkfs.ext4 /dev/XXXX;`

Where XXXX = your partition name such as "sda".

In case your external drive was previously mounted, you can use "$ sudo umount /dev/sda" to unmount.

`$lsblk -o NAME,MOUNTPOINT,UUID,FSTYPE,SIZE,LABEL,MODEL;`

Make note of your external drive's UUID.

`$sudo nano /etc/fstab;`

Create a new line below the others that reads the following: where "{tab}" is you hitting the tab key.

`UUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX {tab} /mnt/ext {tab} ext4 {tab} defaults,noatime {tab} 0 {tab} 2`

Where the UUID is what you copied from above. Hit ctrl+x, y for yes, & enter to save.

`$sudo mkdir -p /mnt/ext;`

`$sudo mount -a;`

`$df -h /mnt/ext;`

Should return:

`Filesystem Size Used Avail Use% Mounted On
#/dev/sda 1.8T 77M 1.7T 1% /mnt/ext`

Set the owner:

`$sudo chown -R pi:pi /mnt/ext/;`

`$cd /mnt/ext;`

`$sudo mkdir -p bitcoin;`

`$ls -la;`

If owner & group for the new bitcoin folder are root & root, then run:

`$sudo chown -R pi:pi /mnt/ext/bitcoin;`

`$ls -la;`

Bitcoin should now be owned by pi.

Let's test our permissions by creating a file & deleting it:

`$touch bitcoin/test/file;`

`$rm bitcoin/test.file;`

You should not receive any errors. If you do then your drive is mounted as read-only and you need to fix that before proceeding.

Move swap file:

`$sudo nano /etc/dphys-swapfile;`

Scroll down to "CONF_SWAPFILE=100" and put a (#) hashtag infront of it. Hit ctrl+x, y for yes, enter for save.

`$sudo dphys-swapfile install;`
