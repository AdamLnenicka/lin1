**Project Documentation: Implementation of IT Infrastructure for Ubuntu and Debian Servers**

**1. Introduction:**
   This project aims to set up a robust IT infrastructure involving Ubuntu and Debian servers. The infrastructure includes network configuration, hostname settings, DHCP server setup, SSH server configuration, automatic backup scripts, and log file management.

**2. Infrastructure Setup:**
   - **Server Installation:** 
     - One virtual machine (VM) running Ubuntu.
     - Two virtual machines running Debian.
   - **Network Configuration:**
     - Each machine will be connected to two networks: NAT network for internet access and an internal network for communication between VMs.

**3. Hostname Configuration:**
   - Ubuntu client: ubuntu-01
   - Debian servers: debian-01, debian-02

**4. Network Configuration on debian-01:**
   - Static IPv4 address configured on the internal interface (10.0.1.1/24).
   - IPv6 address configured (2001:dead::1/64).
   - Automatic activation of the interface on system startup.
   - Domain name resolution configured using DNS server at 8.8.8.8.

**5. DHCP Server Setup on debian-01:**
   - DHCP server installed and configured to run only on the internal network interface.
   - DHCP server set as authoritative.
   - Domain name set to exam.org.
   - DNS servers configured as Google's public DNS servers (8.8.8.8, 2001:4860:4860::8888).
   - IP addresses assigned in the range 10.0.1.100-200.
   - debian-02 assigned IP address ending with .2.

**6. DHCP Configuration on debian-02 and ubuntu-01:**
   - DHCP client configured on debian-02 and ubuntu-01.
   - Functionality of DHCP server verified.

**7. SSH Server Setup on debian-02:**
   - SSH server installed and configured.
   - User 'student' allowed to connect from other machines without password authentication.
   - Directory /share created to store backups with proper permissions.

**8. Automatic Backup Script Setup:**
   - Backup script created on ubuntu-01 and debian-01 to backup the home directory of user 'student'.
   - Script scheduled to run every half an hour.
   - Backups sent to debian-02's /share directory.
   - Completion time logged in /var/log/backups.log.

**9. Log File Management:**
   - Log file /var/log/backups.log rotated when reaching 500 KB.
   - Historical log files compressed and the last 5 files retained.

**10. NFS Share Setup:**
   - NFS share configured on debian-02 for the /share directory.
   - Automatic mounting of the NFS share set up on ubuntu-01 for the /backups directory.

**11. Test Packages Bash Script (test_packages.sh):**
- A bash script named 'test_packages.sh' has been crafted on the ubuntu-01 client to ascertain the presence of critical utilities within the system. The script systematically checks for the existence of essential packages such as tar, telnet, and htop. Upon execution, it diligently verifies the installation status of each package and promptly communicates the result to the user via the terminal interface. This script offers a convenient means of ensuring the availability of fundamental tools essential for system functionality. It resides in the home directory of the user 'student', offering ease of access and execution.

**12. WordPress Installation and Configuration:**
- On the ubuntu-01 server, the WordPress content management system has been meticulously installed and configured to establish a robust web publishing platform. Attention to security measures was paramount throughout the setup process to fortify the system against potential vulnerabilities. Following the installation steps, including downloading the latest WordPress version, configuring database settings, and executing the installation script, a secure WordPress environment was established. By implementing security measures such as password strength enforcement, regular updates, and access restrictions, a resilient WordPress website has been erected, poised for content creation and dissemination. Upon accessing the server, users are seamlessly directed to the WordPress homepage, ushering in a seamless browsing experience.
