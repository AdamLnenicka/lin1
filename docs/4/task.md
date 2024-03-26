
### Na serveru Debian-02:

1. **Nastavení rozhraní pro DHCP:**
     ```
     sudo nano /etc/network/interfaces
     ```
     ```
     iface eth0 inet dhcp
     ```

2. **Restartování síťových služeb:**
     ```
     sudo systemctl restart networking
     ```

### Na klientovi Ubuntu-01:

1. **Nastavení rozhraní pro DHCP:**
     ```
     sudo nano /etc/netplan/01-netcfg.yaml
     ```
     ```
     network:
         version: 2
         renderer: networkd
         ethernets:
             eth0:
                 dhcp4: true
     ```
     
2. **Aplikace změn v konfiguraci:**
     ```
     sudo netplan apply
     ```

### Ověření funkčnosti:

1. **Zkontrolování přidělených IP adres:**
   - Na serveru Debian-02 `ip addr show`.
   - Na klientovi Ubuntu-01 `ip address` nebo `ifconfig`.

2. **Testování konektivity:**
   - `ping <IP_adresa_serveru>`.
