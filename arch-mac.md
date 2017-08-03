## Partitioning

Use DiskUtility to create a partition for Arch.

When you've booted into arch this new empty partition will be called Apple HDFS+ or something to that extent. Use `cgdisk` or `fdisk` to simply delete it so that its now free

To identify what `/dev/sdX` device is your primary hard drive:

`fdisk -l`
