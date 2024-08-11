# Managing multiple Linux distributions on a single system 

## Dual Booting

1. **Install Multiple Distros**:
   - You can install multiple Linux distributions on separate partitions of your hard drive. During the installation process, ensure you select the correct partition for each distro.
   - Use a tool like **GParted** to manage your partitions:
     ```bash
     sudo apt-get install gparted
     sudo gparted
     ```

2. **Configure GRUB**:
   - GRUB (GRand Unified Bootloader) will allow you to select which OS to boot into. After installing multiple distros, update GRUB to include all installed systems:
     ```bash
     sudo update-grub
     ```

## Using Ventoy

1. **Install Ventoy**:
   - Ventoy is a tool that allows you to boot multiple Linux distributions from a single USB drive without needing to reflash it each time¹.
   - Download and install Ventoy:
     ```bash
     wget https://github.com/ventoy/Ventoy/releases/download/v1.0.76/ventoy-1.0.76-linux.tar.gz
     tar -xvf ventoy-1.0.76-linux.tar.gz
     cd ventoy-1.0.76
     sudo ./Ventoy2Disk.sh -i /dev/sdX
     ```
   - Replace `/dev/sdX` with your USB drive identifier.

2. **Add ISOs to Ventoy**:
   - Simply copy the ISO files of the distributions you want to the USB drive. Ventoy will automatically detect and list them at boot.

## Using Distrobox

1. **Install Distrobox**:
   - Distrobox allows you to run multiple Linux distributions inside the terminal using Docker or Podman²³.
   - Install Docker or Podman:
     ```bash
     sudo apt-get install docker.io
     ```
   - Install Distrobox:
     ```bash
     curl -s https://raw.githubusercontent.com/89luca89/distrobox/main/install | sudo sh
     ```

2. **Create and Manage Containers**:
   - Create a new container with a specific distro:
     ```bash
     distrobox-create --name my-container --image ubuntu:latest
     ```
   - Enter the container:
     ```bash
     distrobox-enter my-container
     ```

## Additional Resources

- [(1) How to Boot Multiple Linux Distributions With Ventoy.](https://www.howtogeek.com/802328/how-to-boot-multiple-linux-distributions-with-ventoy/.)
- [(2) How to Run Multiple Linux Distributions Inside the Terminal Using Distrobox.](https://www.makeuseof.com/run-multiple-linux-distros-inside-terminal-distrobox/.)
- [(3) DistroBox: Try Out Multiple Linux Distributions via the Terminal.](https://linuxtldr.com/installing-distrobox/.)
- [(4) en.wikipedia.org.](https://en.wikipedia.org/wiki/Linux_distribution.)