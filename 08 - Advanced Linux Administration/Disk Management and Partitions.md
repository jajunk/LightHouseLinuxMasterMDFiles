# Disk Management and Partition Tables

1. **Graphical Tools**:
   - **GParted**: A powerful graphical partition manager.
     - **Installation**: You can install GParted via the terminal or the graphical software manager.
     - **Features**:
       - Create, resize, move, and delete partitions.
       - Easily manage disk space.
       - User-friendly interface for complex operations.
     - **Usage**:
       - Launch GParted from the menu.
       - Select your disk and perform the desired actions⁴.

   - **Gnome Disks**: The default utility in Linux Mint.
     - **Features**:
       - Provides a visual breakdown of storage devices.
       - Shows partitions, volumes, capacities, and mount points.
     - **Usage**:
       - Open "Disks" from the menu.
       - Explore your disks and partitions.

2. **Command-Line Tools**:
   - **fdisk**: A text-based utility for managing partitions.
     - **Usage**:
       - Identify the disk you want to partition using `lsblk`.
       - Launch fdisk: `sudo fdisk /dev/sdX` (replace `X` with your disk identifier).
       - Follow on-screen prompts to create a new partition.
       - Write changes and exit fdisk¹.


- [(1) How to Install GParted on Linux Mint 21 - Linux Genie.](https://linuxgenie.net/how-to-install-gparted-on-linux-mint-21/.)
- [(2) Linux Mint View & Manage System Partitions: A Comprehensive Guide.](https://bytebitebit.com/tips-tricks/linux-mint-view-manage-system-partitions/.)
- [(3) Linux Mint View Manage System Partitions: A Comprehensive Guide.](https://www.positioniseverything.net/linux-mint-view-manage-system-partitions/.)
- [(4) How to Use Fdisk to Manage Partitions on Linux - How-To Geek.](https://www.howtogeek.com/106873/how-to-use-fdisk-to-manage-partitions-on-linux/.)