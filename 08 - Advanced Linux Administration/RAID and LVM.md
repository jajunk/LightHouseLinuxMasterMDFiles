# RAID and LVM

## 1. **RAID (Redundant Array of Independent Disks)**:
   - RAID combines multiple physical disks into a single logical unit for improved performance, redundancy, and fault tolerance.
   - Common RAID levels:
     - **RAID 0 (Striping)**: Data is split across disks for speed but lacks redundancy.
     - **RAID 1 (Mirroring)**: Data is duplicated on two disks for fault tolerance.
     - **RAID 5 (Striping with Parity)**: Balances speed and redundancy using distributed parity.
     - **RAID 10 (Combination of Mirroring and Striping)**: Provides both speed and redundancy.
   - Hardware RAID uses a dedicated controller, while software RAID relies on the operating system.

## 2. **LVM (Logical Volume Manager)**:
   - LVM abstracts storage management by creating logical volumes (LVs) from physical volumes (PVs).
   - Key features:
     - **Flexibility**: Resize LVs easily without repartitioning.
     - **Volume snapshots**: Create point-in-time copies.
     - **Striping**: Distribute data across multiple PVs.
     - **Mirroring**: Duplicate data for redundancy.


- [(1) Complete Beginner's Guide to LVM in Linux [With Hands-on].](https://linuxhandbook.com/lvm-guide/.)
- [(2) raid - RAIDing with LVM vs MDRAID - Unix & Linux Stack Exchange.](https://unix.stackexchange.com/questions/150644/raiding-with-lvm-vs-mdraid-pros-and-cons.)
