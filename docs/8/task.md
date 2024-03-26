### Na serveru Debian-02:

1. **Instalace NFS serveru:**
   ```bash
   sudo apt update
   sudo apt install nfs-kernel-server
   ```

2. **Konfigurace sdíleného adresáře:**
     ```bash
     sudo nano /etc/exports
     ```
     ```
     /share ubuntu-01(rw,sync,no_subtree_check)
     ```

3. **Aktualizace exportovaných adresářů:**
   ```bash
   sudo exportfs -a
   ```

4. **Restart NFS služby:**
   ```bash
   sudo systemctl restart nfs-kernel-server
   ```

### Na klientovi Ubuntu-01:

1. **Instalace NFS klienta:**
   ```bash
   sudo apt update
   sudo apt install nfs-common
   ```

2. **Vytvoření adresáře pro připojení:**
   ```bash
   sudo mkdir /mnt/backups
   ```

3. **Automatické připojení NFS exportu:**
     ```bash
     sudo nano /etc/fstab
     ```
     ```
     debian-02:/share /mnt/backups nfs rw,sync,hard,intr 0 0
     ```

4. **Připojení NFS exportu:**
   na klientovi Ubuntu-01:
     ```bash
     sudo mount -a
     ```
