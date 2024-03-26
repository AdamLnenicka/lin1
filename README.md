# Project Documentation
The project involves setting up network connectivity, DHCP services, backup solutions, web server deployment, and more using Ubuntu client and Debian Servers.

### Project Specifications
- Ubuntu VM: 1 instance
- Debian VMs: 2 instances
- Network Configuration:
  - NAT for internet access
  - Internal network for VM communication
- Implementation Tasks:
  1. Hostname Configuration
  2. Static IP and DHCP Server Configuration on Debian-01
  3. DHCP Server Configuration on Debian-01
  4. DHCP Client Configuration on Debian-02 and Ubuntu-01
  5. Backup Server Configuration on Debian-02
  6. Backup Script Implementation
  7. Log Rotation Configuration
  8. NFS Share Setup
  9. Package Testing Script on Ubuntu-01
  10. Wordpress Installation on Ubuntu-01
  11. Ansible Controller Setup on Ubuntu-01
  12. iSCSI Configuration on Debian-01
  13. iSCSI Configuration on Debian-02
  14. Apache Installation and Virtual Host Setup on Debian-02
  15. Web Accessibility Configuration

## Implementation Details

### 1. Hostname Configuration
- Ubuntu VM: `ubuntu-01`
- Debian VMs: `debian-01`, `debian-02`

### 2. Static IP and DHCP Server Configuration on Debian-01
- Internal Interface:
  - IPv4 Address: `10.0.1.1/24`
  - IPv6 Address: `2001:dead::1/64`
  - DNS Server: `8.8.8.8`
- DHCP Server Configuration:
  - Authoritative
  - Domain Name: `exam.org`
  - DNS Servers: `8.8.8.8`, `2001:4860:4860::8888`
  - IP Range: `10.0.1.100-10.0.1.200`

### 3. DHCP Server Configuration on Debian-01
- Restricted to Internal Interface
- Authoritative Configuration

### 4. DHCP Client Configuration on Debian-02 and Ubuntu-01
- Obtaining IP Addresses from DHCP Server
- Verification of Functionality

### 5. Backup Server Configuration on Debian-02
- SSH Server Installation
- User Configuration (`student`)
- Directory Setup (`/share`)
- Permissions Management

### 6. Backup Script Implementation
- Automatic Backup Script Creation
- Interval: Every 30 minutes
- Backup Destination: `debian-02:/share`
- Logging: `/var/log/backups.log`

### 7. Log Rotation Configuration
- Rotation Size: 500 KB
- Retention Policy: Last 5 Logs
- Compression of Historical Logs

### 8. NFS Share Setup
- Share Configuration: `/share` on Debian-02
- Automatic Mounting on Ubuntu-01

### 9. Package Testing Script on Ubuntu-01
- Script Name: `test_packages.sh`
- Checks for: `tar`, `telnet`, `htop`
- Status Reporting: Installed/Not Installed

### 10. Wordpress Installation on Ubuntu-01
- Secure Installation of Wordpress
- Initial Configuration
- Landing Page Setup

### 11. Ansible Controller Setup on Ubuntu-01
- Inventory Creation
- Ping Test Script Creation (`ping.sh`)
- Connectivity Testing to All Servers

### 12. iSCSI Configuration on Debian-01
- Connection to iSCSI Device on Debian-02
- GPT Partition Table Creation
- Filesystem Setup: `ext3` and `NTFS`
- Automatic Mounting on System Startup

### 13. iSCSI Configuration on Debian-02
- Creation of `disk.img` File
- iSCSI Sharing Configuration
- CHAP Authentication Setup

### 14. Apache Installation and Virtual Host Setup on Debian-02
- Apache Installation
- Virtual Host Configuration
- Custom Static Website Deployment

### 15. Web Accessibility Configuration
- Domain: `www.test2024.com`
- Accessibility from Ubuntu-01 Client and functionality of the network infrastructure.
