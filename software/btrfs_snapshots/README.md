# BTRFS Snapshot Example

## Overview

This example demonstrates how to create a BTRFS snapshot, and shows that the snapshot
uses minimum additional space.

An empty file is created to hold the BTRFS filesystem.  This file is mounted using the Linux loop device.

The script performs the following steps:
- Create an empty file to use as a disk image
- Create a BTRFS filesystem within the disk image file created in the previous step
- Mount the disk image using the loop device (mount -o loop)
- Create two BTRFS subvolumes -- one to hold working files, and one to hold snapshots
- Create four large files in the "working" directory
- Create a snapshot of the "working" directory in the "snapshots" directory, showing
that disk usage is the same before and after the snapshot is created.
- Modify one of the working files, then show that this caused the disk usage to increase
- Drop the file modification by restoring the file's original contents from the snapshot.  Note that the when the file is restored to its original contents, the disk usage decreases.


## Prerequisites
- "btrfs-progs" must be installed
- You must have "sudo" access on the computer where you run "create"
    - Sudo is required to mount and unmount the BTRFS volume
    - NOTE: Review the script's use of sudo to ensure you are ok with how the script uses sudo before running

## Running the Example
- "create" runs the example
- "clean" deletes working files created by "create"

## References
-  [BTRFS Snapshots](https://www.retired-engineer.com/software/btrfs_snapshots) post on the [Retired Engineer](https://www.retired-engineer.com) blog.
