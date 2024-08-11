# Comprehensive Linux Network Troubleshooting Guide

## 1. Basic Network Configuration Check:

   - Check IP address and network interface status:
     ```
     ip addr show
     ```
     or (for older systems):
     ```
     ifconfig -a
     ```
   - Verify default gateway:
     ```
     ip route show
     ```
   - Check DNS configuration:
     ```
     cat /etc/resolv.conf
     ```

## 2. Network Interface Configuration:

   - Edit network interface configuration:
     ```
        - For Linux Mint and some other distributions:
     ```
     sudo nano /etc/network/interfaces.d/wlan0.cfg  # for wireless
     ```
   - Restart specific network interface:
     ```
     sudo ifdown eth0 && sudo ifup eth0
     ```
     or
     ```
     sudo ip link set eth0 down && sudo ip link set eth0 up
     ```

## 3. Connectivity Tests:

   - Ping test:
     ```
     ping -c 4 8.8.8.8
     ```
   - Traceroute:
     ```
     traceroute google.com
     ```
   - DNS resolution test:
     ```
     nslookup google.com
     ```
     or
     ```
     dig google.com
     ```

## 4. Advanced Diagnostic Tools:

   - netstat or ss:
     ```
     netstat -tuln
     ```
     or
     ```
     ss -tuln
     ```
   - tcpdump:
     ```
     sudo tcpdump -i eth0
     ```
   - nmap:
     ```
     nmap -p- localhost
     ```

## 5. Firewall Configuration:

   - Check iptables rules:
     ```
     sudo iptables -L -v -n
     ```
   - Temporarily disable firewall (for testing):
     ```
     sudo systemctl stop firewalld  # for systems using firewalld
     ```
     or
     ```
     sudo ufw disable  # for systems using ufw
     ```

## 6. Network Service Diagnostics:

   - Check service status:
     ```
     systemctl status networking
     ```
     or
     ```
     systemctl status NetworkManager
     ```
   - Restart network service:
     ```
     sudo systemctl restart networking
     ```
     or
     ```
     sudo systemctl restart NetworkManager
     ```
   - For some distributions (e.g., Linux Mint):
     ```
     sudo service network-manager restart
     ```

## 7. Wireless Network Troubleshooting:

   - List available wireless networks:
     ```
     sudo iwlist wlan0 scan
     ```
   - Check wireless interface details:
     ```
     iwconfig
     ```
   - Monitor wireless connection in real-time:
     ```
     watch -n 1 iwconfig
     ```
   - Additional Wi-Fi troubleshooting steps:
     - Confirm Wi-Fi adapter is enabled and connected
     - Update Linux kernel and drivers
     - Disable power management for Wi-Fi
     - Consider using a USB Wi-Fi adapter if internal cards are faulty

## 8. Advanced Network Analysis:

   - Wireshark: GUI-based packet analyzer
   - iftop: Displays bandwidth usage on an interface
   - nethogs: Groups bandwidth by process

## 9. Performance Testing:

   - iperf: Network performance measurement tool
   - speedtest-cli: Command-line interface for testing internet speed

## 10. Log Analysis:

    - System logs:
      ```
      sudo tail -f /var/log/syslog  # on Debian-based systems
      ```
      or
      ```
      sudo tail -f /var/log/messages  # on Red Hat-based systems
      ```
    - Network-specific logs:
      ```
      sudo tail -f /var/log/daemon.log
      ```

## 11. Network Configuration Backup and Restore:

    - Backup network configuration:
      ```
      sudo tar -czvf network_config_backup.tar.gz /etc/network
      ```
    - Restore network configuration:
      ```
      sudo tar -xzvf network_config_backup.tar.gz -C /
      ```

## 12. Troubleshooting Specific Issues:

    - High latency: Use ping and traceroute to identify where delays occur
    - Packet loss: Use mtr (My TraceRoute) for a combination of ping and traceroute
    - DNS issues: Check /etc/hosts file and DNS server configurations
    - IP conflicts: Use arping to detect duplicate IP addresses on the network