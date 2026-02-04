# DevOps Beginner Practical Series

This file contains step-by-step practical exercises for learning DevOps using VirtualBox and Ubuntu Server.

---

## Practical 1: Install VirtualBox

### Steps

1. **Open Web Browser**
   - Chrome, Edge, or Firefox.

2. **Go to the Official VirtualBox Website**

https://www.virtualbox.org

- Press Enter.

3. **Navigate to Downloads**
- Click **Downloads** in the top menu.

4. **Choose Your Operating System**
- Windows hosts → Windows
- macOS hosts → Mac
- Linux distributions → Linux

5. **Locate the Downloaded Installer**
- Check your **Downloads** folder.

6. **Start Installation**
- Double-click the installer file.
- Click **Yes / Allow** if prompted.

7. **Follow Installation Wizard**
- Click **Next**, leave default settings.
- Click **Install**.

8. **Finish Installation**
- Click **Finish** when done.

9. **Verify Installation**
- Open VirtualBox.
- You should see the home screen with options: New, Add, Settings.

---

## Practical 2: Download Ubuntu Server OS

### Why Ubuntu Server?
- Most popular DevOps server OS  
- Lightweight  
- Free  
- Strong community  

### Steps

1. Open browser → `https://ubuntu.com`
2. Navigate to **Download → Ubuntu Server**
3. Choose **Ubuntu Server LTS**
- LTS = Long Term Support
4. Start download (file format: `.iso`)
5. Confirm download in **Downloads** folder

---

## Practical 3: Create a Virtual Machine

### VM Configuration
- Name: `devops-server`  
- Type: Linux  
- Version: Ubuntu (64-bit)  
- RAM: 2GB  
- CPU: 2 cores  
- Disk: 20GB (dynamically allocated)  
- Attach Ubuntu ISO to optical drive  

### Steps

1. Open VirtualBox → Click **New**
2. Name: `devops-server`, Type: Linux, Version: Ubuntu (64-bit)
3. Allocate RAM: 2048 MB
4. Create virtual hard disk → VDI → Dynamically allocated → 20 GB
5. Attach ISO: Settings → Storage → Optical Drive → Choose ISO
6. Start VM

---

## Practical 4: Install Linux Inside the VM

### Steps

1. Start VM → Ubuntu installer appears
2. Select **Language**
3. Select **Keyboard layout**
4. Network: Accept **DHCP** (auto-configured)
5. Create User:
- Username: e.g., `devops`
- Password
6. Enable OpenSSH
7. Finish installation → Reboot VM
8. Log in with created username/password

---

## Practical 5: First Server Commands (Very Important)

### Commands

```bash
whoami
hostname
pwd
ls
uname -a
lsb_release -a

```

## Practical 6: Networking in a VM

### Step 1: Open the VM Terminal
- Log in to your Ubuntu Server VM (`devops-server`)  
- You should see the terminal prompt:

devops@devops-server:~$


### Step 2: Check Network Configuration
```bash
ip a
```

Shows all network interfaces and IP addresses

Example output:
1: lo: <LOOPBACK,UP,LOWER_UP> ...
    inet 127.0.0.1/8
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> ...
    inet 10.0.2.15/24

Step 3: Key Concepts

Virtual NIC (vNIC): Virtual network card that allows the VM to communicate with host or internet.

Private IP: Internal IP assigned to the VM, not directly accessible from the internet.

NAT vs Bridged Networking:

NAT → VM shares host’s internet (default for beginners)

Bridged → VM appears as a separate device on the network

Step 4: Optional Connectivity Test
ping -c 4 8.8.8.8


Confirms that the VM has internet access.

# VirtualBox Ubuntu VM Practical Labs (Continued)

## Practical 7: Install a Real Service (Mini Project)
**Project:** Host a Web Server (Nginx)

### Step 1: Update the Server
```bash
sudo apt update

```

Updates package lists to get the latest software versions.

Step 2: Install Nginx
Bashsudo apt install nginx -y

Installs Nginx web server.
-y automatically confirms installation prompts.

Step 3: Check Service Status
Bashsudo systemctl status nginx

Checks if Nginx is running.
Look for: Active: active (running)

Step 4: Access the Web Server
Open a browser on the host machine:

NAT mode → http://localhost
Bridged mode → http://<VM-IP>
(Find VM IP using ip a or ip addr)

You should see the default Nginx welcome page.
Step 5: Key Concepts

Services — Programs running in the background
systemd — System and service manager in modern Linux
Background processes — Continue running even after terminal is closed


Practical 8: Modify the Website
Step 1: Navigate to Web Root
Bashcd /var/www/html

Default folder where Nginx serves web content

Step 2: Open index.html
Bashsudo nano index.html

Opens the main HTML file using the nano text editor

Step 3: Replace Content
Replace the existing content with:
HTML<h1>My First VM Server</h1>
<p>Running on a Virtual Machine</p>
Step 4: Save and Exit nano

Ctrl + O → Save
Enter → Confirm filename
Ctrl + X → Exit

Step 5: Reload Browser
Refresh:

http://localhost (NAT)
or http://<VM-IP> (Bridged)

You should now see your custom message.
Step 6: Key Concepts

/var/www/html — Default Nginx web root directory
nano — Beginner-friendly command-line text editor
Web changes are reflected immediately (no need to restart Nginx)


Practical 9: Resource Monitoring
Step 1: Check CPU Usage
Bashtop

Shows real-time CPU usage and running processes
%CPU column — shows CPU usage per process
Press q to exit

Step 2: Check Memory Usage
Bashfree -h

Displays RAM usage in human-readable format (-h)
used — memory currently in use
free — memory still available
swap — disk-based backup memory

Step 3: Check Disk Usage
Bashdf -h

Shows disk space usage for all mounted filesystems
Columns: Size, Used, Avail, Use%, Mounted on

Step 4: Key Concepts

CPU Usage — Measures how busy the processor is
Memory Usage — Tracks RAM utilization
Disk Usage — Shows available storage space

Step 5: Quick Exercise

Run top, free -h, and df -h to observe current usage
Open a second terminal and run stress commands:Bashping 8.8.8.8
# or
yes > /dev/null
Watch top again to see increased CPU/memory usage


Practical 10: Snapshot & Recovery
Step 1: Take a Snapshot

In VirtualBox → Select your VM
Go to Snapshots tab (top right)
Click Take (camera icon)
Name: Before Modifications
(Optional) Add a description
Click OK

Step 2: Shutdown the VM
Clean shutdown (preferred):
Bashsudo shutdown now
Or from VirtualBox menu:
Close → ACPI Shutdown
Step 3: Restore Snapshot

Snapshots tab → Select the snapshot
Click Restore
Confirm the action

Step 4: Restart the VM

Select VM → Click Start

→ VM returns to the exact state when the snapshot was taken.
Step 5: Key Concepts

Snapshot — Captures point-in-time state of the entire VM
Shutdown — Ensures safe state and data integrity before snapshot/restore
Recovery — Quick rollback for testing, mistakes, or experiments

Step 6: Quick Exercise

Take a snapshot named "Before Changes"
Make modifications (edit website, install packages, etc.)
Restore the snapshot
Start VM and verify it returned to the original state
