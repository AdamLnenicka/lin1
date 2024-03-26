
### Na klientovi Debian-01:

1. **Instalace iSCSI Initiatoru:**
   ```bash
   sudo apt update
   sudo apt install open-iscsi
   ```

2. **Konfigurace iSCSI Initiatoru:**
     ```bash
     sudo nano /etc/iscsi/initiatorname.iscsi
     ```
     ```
     InitiatorName=iqn.2022-03.com.example:debian01
     ```

3. **Připojení iSCSI zařízení:**
     ```bash
     sudo iscsiadm --mode discovery --type sendtargets --portal [IPv6_adresa_serveru]:3260
     ```
     ```bash
     sudo iscsiadm --mode node --targetname iqn.2022-03.com.example:disk01 --portal [IPv6_adresa_serveru]:3260 --login
     ```

4. **Vytvoření tabulky oddílů GPT:**
     ```bash
     sudo parted /dev/sdX mklabel gpt
     ```

5. **Vytvoření oddílů:**
     ```bash
     sudo mkfs.ext3 /dev/sdX1
     ```
     ```bash
     sudo mkfs.ntfs /dev/sdX2
     ```

6. **Vytvoření adresářů pro připojení:**
   ```bash
   sudo mkdir /mnt/ext3 /mnt/ntfs
   ```

7. **Připojení oddílů:**
     ```bash
     sudo mount /dev/sdX1 /mnt/ext3
     ```
     ```bash
     sudo mount /dev/sdX2 /mnt/ntfs
     ```

8. **Nastavení oprávnění pro uživatele student:**
   ```bash
   sudo chown -R student:student /mnt/ext3 /mnt/ntfs
   ```

9. **Konfigurace automatického připojení:**
     ```
     /dev/sdX1 /mnt/ext3 ext3 defaults 0 0
     /dev/sdX2 /mnt/ntfs ntfs defaults 0 0
     ```
