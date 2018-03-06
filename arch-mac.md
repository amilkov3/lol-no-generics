# Unfinished

## Partitioning

Use DiskUtility to create a partition for Arch.

When you've booted into arch this new empty partition will be called Apple HDFS+ or something to that extent. Use `cgdisk` or `fdisk` to simply delete it so that its now free

To identify what `/dev/sdX` device is your primary hard drive:

`fdisk -l`

To proceed with partitioning the device:

`fdisk /dev/sdX`

We start by creating our root (/) mount point which we want to be about 20 GB

Command: n
Partition number: <default 7>
First sector: <default>
Last sector: +20GB

Next we need to create a swap space for RAM spill over. This should be about 8 GB

Command: n
Partition number: <default 8>
First sector: <default>
Last sector: +8GB

