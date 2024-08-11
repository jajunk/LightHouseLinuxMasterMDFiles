# Network Troubleshooting

## 1. **Check Network Interfaces**:
   - Use the `ifconfig -a` command in the terminal to list available network interfaces and their details¹.
   - Alternatively, access the graphical network manager by clicking the network icon in the system tray and selecting "Network Settings."

## 2. **Configure Network Interfaces**:
   - Edit the network configuration file for the desired interface (e.g., `wlan0.cfg`) using `sudo nano /etc/network/interfaces.d/wlan0.cfg`¹.
   - Specify IP address, netmask, gateway, DNS servers, etc., in the configuration file.

## 3. **Restart Network Manager**:
   - Sometimes restarting the Network Manager helps resolve connectivity issues. Run: `sudo service network-manager restart`⁴.

## 4. **Wi-Fi Troubleshooting**:
   - Confirm Wi-Fi adapter is enabled and connected.
   - Update Linux kernel and drivers.
   - Disable power management for Wi-Fi.
   - Consider using a USB Wi-Fi adapter if internal cards are faulty.

(1) The Ultimate Guide to Linux Mint Network Configuration. https://www.fosslinux.com/105545/the-ultimate-guide-to-linux-mint-network-configuration.htm.
(2) Linux Mint Troubleshooting Guide: Solutions to Common Issues. https://www.fosslinux.com/104779/the-guide-to-troubleshooting-common-linux-mint-issues.htm.
(3) 13 Linux Network Configuration and Troubleshooting Commands - Tecmint. https://www.tecmint.com/linux-network-configuration-and-troubleshooting-commands/.
(4) A beginner's guide to network troubleshooting in Linux. https://www.redhat.com/sysadmin/beginners-guide-network-troubleshooting-linux.