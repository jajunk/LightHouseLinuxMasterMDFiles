# Installing Device Drivers

## Installing Device Drivers on Linux Mint

1. **Using Driver Manager**:
   - **Open Driver Manager**: You can find it in the Menu or by searching for "Driver Manager".
   - **Check for Available Drivers**: The Driver Manager will list available drivers for your hardware.
   - **Select and Install**: Choose the drivers you need and click "Apply Changes".
   - **Reboot**: Restart your system to apply the changes¹.

### 2. **Manual Installation via Terminal**:
   - **Identify Hardware**: Use the `inxi` command to list your hardware:
     ```bash
     inxi -Fzx
     ```
   - **Install Drivers**: For example, to install NVIDIA drivers:
     ```bash
     sudo apt-get install nvidia-driver-460
     ```
   - **Reboot**: Restart your system to apply the changes¹.

## Installing Drivers in Containers

### 1. **Create and Start a Container**:
   - Create a container:
     ```bash
     sudo lxc-create -n my-container -t download
     ```
   - Start the container:
     ```bash
     sudo lxc-start -n my-container
     ```

### 2. **Access the Container**:
   - Attach to the container:
     ```bash
     sudo lxc-attach -n my-container
     ```

### 3. **Install Drivers Inside the Container**:
   - Once inside the container, you can install drivers just like on the host system. For example, to install a network driver:
     ```bash
     sudo apt-get update
     sudo apt-get install firmware-realtek
     ```


- [(1) How to Install Essential Hardware Drivers on Linux Mint.](https://www.fosslinux.com/134500/how-to-install-necessary-hardware-drivers-on-linux-mint.htm.)
- [(2) How to Install Hardware Drivers on Linux - How-To Geek.](https://www.howtogeek.com/213488/how-to-install-hardware-drivers-on-linux/.)
