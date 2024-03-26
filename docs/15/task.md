### Na serveru Debian-02:

1. **Přidání aliasu pro doménu www.test2024.com:**
     ```bash
     sudo nano /etc/apache2/sites-available/novy_virtualhost.conf
     ```
   - Přidejte alias pro doménu `www.test2024.com`:
     ```apache
     <VirtualHost *:80>
         ServerAdmin webmaster@example.com
         ServerName novy_virtualhost
         ServerAlias www.test2024.com   # Přidat tento řádek
         DocumentRoot /home/web
         ...
     ```

2. **Aktualizace konfigurace Apache:**
   - Aktualizujte konfiguraci Apache:
     ```bash
     sudo a2ensite novy_virtualhost.conf
     sudo systemctl restart apache2
     ```

### Na klientovi Ubuntu-01:
 **Aktualizace souboru hosts:**
     ```bash
     sudo nano /etc/hosts
     ```
     ```
     <IP_adresa_Debian-02>   www.test2024.com
     ```
