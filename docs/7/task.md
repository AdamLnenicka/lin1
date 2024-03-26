
1. **Vytvoření konfiguračního souboru pro logrotate:**
   - Otevřete konfigurační soubor pro logrotate:
     ```
     sudo nano /etc/logrotate.d/backups
     ```
   - Vložte následující obsah do souboru:
     ```
     /var/log/backups.log {
         size 500k
         rotate 5
         compress
         missingok
         notifempty
         create 0644 root root
     }
     ```

2. **Spouštění `logrotate` manuálně pro ověření:**
     ```
     sudo logrotate -vf /etc/logrotate.d/backups
     ```
