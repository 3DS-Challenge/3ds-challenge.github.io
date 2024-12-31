# Mount CTRNAND on a PC
For Windows, OSFMount can be used. For Linux, follow the instructions below to mount.

## Instructions (Linux)
1. Run `sudo losetup -f -P ctrnand_full.img`. -f is to find the first unused loop device and -P is to scan for partitions.
2. If running the previous command does not return any output, run `lsblk` and look for a loop device of about 734 MB. Copy the largest partition for that loop device (e.g. `/dev/loop0p1`).
3. Run `mkdir /tmp/mount`.
4. Run `sudo mount -o ro (loop device partition) /tmp/mount`.
5. Navigate to `/tmp/mount` to view the contents of the CTRNAND.
6. When finished using the mount, run `sudo umount /tmp/mount` to unmount the loop device from the temp directory, and then run `sudo losetup -d (loop device)` to detach the loop device, or run `sudo losetup -D` to detach all loop devices.

## PLEASE NOTE
If you used anything other than get-ctr-stuff to extract the contents of an X1(A/B) nand, part of the MBR headers will need to be filled with zeros to remove garbage data that prevents the image from being readable. For ctrnand_full, these offsets are 0x1CE - 0x1FD. For twlnand_full, these offsets are 0x1DE - 0x1FD.
