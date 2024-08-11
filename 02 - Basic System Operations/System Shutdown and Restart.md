# Comprehensive Guide to Linux Shutdown and Restart Procedures

## 1. Basic Command Line Methods

### Shutdown
- Immediate shutdown: 
  ```bash
  sudo shutdown -h now
  ```
- Shutdown after a delay: 
  ```bash
  sudo shutdown -h +m
  ```
  (replace m with number of minutes)
- Shutdown at a specific time: 
  ```bash
  sudo shutdown -h HH:MM
  ```
  (24-hour format)

### Restart
- Immediate restart: 
  ```bash
  sudo shutdown -r now
  ```
  or
  ```bash
  sudo reboot
  ```
- Restart after a delay: 
  ```bash
  sudo shutdown -r +m
  ```
  (replace m with number of minutes)
- Restart at a specific time: 
  ```bash
  sudo shutdown -r HH:MM
  ```
  (24-hour format)

### Cancel a scheduled shutdown or restart
```bash
sudo shutdown -c
```

## 2. Using systemctl (for systemd-based distributions)

- Shutdown: 
  ```bash
  sudo systemctl poweroff
  ```
- Restart: 
  ```bash
  sudo systemctl reboot
  ```

## 3. Legacy Commands

These still work on most systems:
- Shutdown: 
  ```bash
  sudo halt
  ```
  or 
  ```bash
  sudo poweroff
  ```
- Restart: 
  ```bash
  sudo reboot
  ```

## 4. GUI Methods

Most desktop environments (GNOME, KDE, Xfce, etc.) have a menu option for shutting down or restarting. These are usually found in the main menu or by clicking on the user name/icon.

## 5. Emergency Immediate Shutdown

In case of an unresponsive system, use the magic SysRq key combinations:
- Hold Alt + SysRq (usually Print Screen), then press these keys in sequence: R E I S U B
- This safely syncs data, unmounts filesystems, and reboots the system

## 6. Sending Signals

You can use the `kill` command to send signals to the init process:
- Shutdown: 
  ```bash
  sudo kill -s SIGINT 1
  ```
- Restart: 
  ```bash
  sudo kill -s SIGTERM 1
  ```

## 7. Additional Options and Considerations

- Force shutdown (use cautiously): 
  ```bash
  sudo shutdown -h -f now
  ```
- Schedule a shutdown message: 
  ```bash
  sudo shutdown -h +m "System will shutdown in m minutes"
  ```
- Shut down without sudo (if configured): 
  ```bash
  shutdown -h now
  ```

## 8. Shutting Down Remote Systems

- SSH into the system and use any of the above commands
- Use 
  ```bash
  ssh user@host "sudo shutdown -h now"
  ```
  from another machine

## 9. Checking Shutdown/Restart History

- View last shutdown: 
  ```bash
  last -x shutdown
  ```
- View last reboot: 
  ```bash
  last reboot
  ```
- Check system logs: 
  ```bash
  journalctl --since "1 hour ago" | grep -i "shut down\|reboot"
  ```

## 10. Best Practices

- Always ensure all important data is saved before shutting down or restarting
- Close all running applications to prevent data loss
- For servers, notify users before scheduling a shutdown or restart
- Use delayed shutdowns to give time for important processes to complete
- Regularly check system logs for any shutdown/restart issues