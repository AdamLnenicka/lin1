postup pro nastavení statické IPv4 a IPv6 adresy na serveru Debian-01:

1. **Připojení k serveru:**
   - přes SSH nebo terminál přímo na serveru.

2. **Nastavení statické IPv4 adresy:**
     ```
     sudo nano /etc/network/interfaces
     ```
     ```
     iface eth0 inet static
         address 10.0.1.1
         netmask 255.255.255.0
     ```

3. **Nastavení IPv6 adresy:**
     ```
     sudo nano /etc/network/interfaces
     ```
     ```
     iface eth0 inet6 static
         address 2001:dead::1
         netmask 64
     ```

4. **Nastavení automatického startu rozhraní:**
     ```
     sudo nano /etc/network/interfaces
     ```
   - Na začátek souboru:
     ```
     auto eth0
     ```

5. **Nastavení DNS serveru:**
   - konfigurační soubor pro DNS resolver:
     ```
     sudo nano /etc/resolv.conf
     ```
   - zjišťování doménových jmen:
     ```
     nameserver 8.8.8.8
     ```

6. **Restartování síťových služeb:**
     ```
     sudo systemctl restart networking
     ```

Debian-01 má nastavenou statickou IPv4 adresu 10.0.1.1 s maskou 255.255.255.0 a IPv6 adresu 2001:dead::1/64. Rozhraní by se mělo automaticky aktivovat po startu systému, a pro zjišťování doménových jmen by měl být použit DNS server na adrese 8.8.8.8.
