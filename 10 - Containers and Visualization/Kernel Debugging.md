# Kernel Debuggings

## Setting Up the Debugging Environment

### 1. **Enable Kernel Debugging Options**:
   - When compiling the kernel, enable debugging options via `make menuconfig`:
     ```bash
     make menuconfig
     ```
     Navigate to "Kernel hacking" and enable options like "Kernel debugging" and "Debug kernel data structures".

### 2. **Install Debugging Tools**:
   - **kdump**: A kernel crash dumping mechanism.
     ```bash
     sudo apt-get install kdump-tools
     sudo systemctl enable kdump
     ```
   - **SystemTap**: For writing and executing scripts that monitor kernel activities.
     ```bash
     sudo apt-get install systemtap systemtap-sdt-dev
     ```

### Using kdump for Crash Dumps

### 1. **Generate Crash Dumps**:
   - Simulate a kernel crash (only in a safe, testing environment):
     ```bash
     echo c > /proc/sysrq-trigger
     ```
   - kdump will create a `vmcore` file in `/var/crash/`.

### 2. **Analyze Crash Dumps**:
   - Use the `crash` tool to analyze `vmcore` files:
     ```bash
     crash /usr/lib/debug/boot/vmlinux-$(uname -r) /var/crash/[timestamp]/vmcore
     ```

#### Using SystemTap for Kernel Monitoring

### 1. **Create SystemTap Scripts**:
   - Example script to monitor system calls:
     ```bash
     probe syscall.* {
       printf("%s called\n", name)
     }
     ```

### 2. **Run SystemTap Scripts**:
   - Execute the script:
     ```bash
     sudo stap yourscript.stp
     ```

#### Advanced Debugging Techniques

### 1. **Dynamic Debugging**:
   - Enable debugging of specific parts of the kernel dynamically:
     ```bash
     echo -n 'module [module_name] +p' > /sys/kernel/debug/dynamic_debug/control
     ```

### 2. **Using ftrace**:
   - Trace kernel functions and events:
     ```bash
     mount -t tracefs nodev /sys/kernel/tracing
     ```

### 3. **Using KGDB**:
   - For single-stepping and debugging kernel/module source code:
     ```bash
     kgdb
     ```

