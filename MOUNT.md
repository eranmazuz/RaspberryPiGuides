# Auto mounting hdd

## Format drive:

Get the hdd drive path (it should be something like /dev/sda):

    sudo fdisk -l

enter format:
    
    sudo fdisk [drive path]

enter the following to format the drive:

* Create a new partition table: g
* Create a new partition: n (press enter for default values)
* Confirm with Y to remove signature
* write changes and exit fdisk: w


format partition:

    sudo mkfs.ext4 [drive path]

create mount point:

    sudo mkdir -p /mnt/usb1

set ownership on the mount point:

    sudo chown -R [user]:[group] /mnt/usb1


## Automount drive:

print the drives information:
    
    sudo blkid

you should have something like this:
    
    [drive path]: UUID="[uuid]" BLOCK_SIZE="4096" TYPE="ext4" PARTUUID="[part uuid]"

enter the fstab file (where we set the mount):

    sudo nano /etc/fstab

add the following line and save:

    UUID=[UUID] /mnt/usb1 [TYPE] defaults,auto,users,rw,nofail,noatime 0 0


unmount the drive

    sudo umount [drive path]

run mount and check if it mounted:

    sudo mount -a