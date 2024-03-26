
### Na serveru Debian-02:

1. **Vytvoření souboru o velikosti 2GB:**
   ```bash
   sudo dd if=/dev/zero of=/disk.img bs=1M count=2048
   ```

2. **Instalace a konfigurace iSCSI Targetu:**
     ```bash
     sudo apt update
     sudo apt install tgt
     ```
   
     ```bash
     sudo nano /etc/tgt/conf.d/disk.img.conf
     ```
   
     ```
     <target iqn.2024-03.exam.test:disk>
         backing-store /disk.img
         incominguser xlnenick libovolne_heslo
     </target>
     ```
     - `iqn.2024-03.exam.test:disk` je doménové jméno IQN.
     - `incominguser xlnenick libovolne_heslo` 

3. **Restartování služby iSCSI Targetu:**
   ```bash
   sudo systemctl restart tgt
   ```
