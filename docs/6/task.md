
### Na serveru Debian-01:

1. **Vytvoření adresáře pro zálohy:**
     ```
     sudo mkdir /home/student/backup
     ```

### Na klientovi Ubuntu-01:

1. **Vytvoření skriptu pro zálohování:**
     ```
     nano backup_script.sh
     ```

2. **Napište obsah skriptu:**
     ```bash
     #!/bin/bash
     
     # Definice proměnných
     TIMESTAMP=$(date +"%Y-%m-%d_%H-%M-%S")
     BACKUP_DIR="/home/student/backup"
     LOG_FILE="/var/log/backups.log"
     
     # Zálohování domovského adresáře
     tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" /home/student
     
     # Zápis do logu
     echo "Backup finished at $(date +"%H:%M")" >> $LOG_FILE
     ```

3. **Nastavení oprávnění:**
     ```
     chmod +x backup_script.sh
     ```

4. **Plánování automatického spouštění:**
   -  `crontab -e`, na konec souboru:
     ```
     */30 * * * * /path/to/backup_script.sh
     ```

5. **Manuální spuštění skriptu:**
     ```
     ./backup_script.sh
     ```
