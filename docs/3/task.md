Zde je podrobný návod pro instalaci a konfiguraci DHCP serveru na serveru Debian-01:

1. **Instalace DHCP serveru:**
     ```
     sudo apt install isc-dhcp-server
     ```

2. **Konfigurace DHCP serveru:**
     ```
     sudo nano /etc/dhcp/dhcpd.conf
     ```
   - úpravy:
       ```
       option domain-name "exam.org";
       ```
     - DNS servery na veřejné servery Google (8.8.8.8 a 2001:4860:4860::8888):
       ```
       option domain-name-servers 8.8.8.8, 2001:4860:4860::8888;
       ```
     - rozsah IP adres
       ```
       subnet 10.0.1.0 netmask 255.255.255.0 {
           range 10.0.1.100 10.0.1.200;
           option routers 10.0.1.1;
           option subnet-mask 255.255.255.0;
       }
       ```
       
4. **Nastavení autoritativního režimu:**
   - na začátek konfiguračního souboru:
     ```
     authoritative;
     ```
     
5. **povolení DHCP serveru na rozhraní:**
     ```
     sudo nano /etc/default/isc-dhcp-server
     INTERFACESv4="eth0"
     INTERFACESv6="eth0"
     ```

6. **Restartování DHCP serveru:**
   - Restartujte DHCP server, aby se změny projevily:
     ```
     sudo systemctl restart isc-dhcp-server
     ```
