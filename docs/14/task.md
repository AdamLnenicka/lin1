
### Na serveru Debian-02:

1. **Instalace Apache:**
   ```bash
   sudo apt update
   sudo apt install apache2
   ```

2. **Vytvoření kořenového adresáře pro novou webovou stránku:**
   ```bash
   sudo mkdir /home/web
   ```

3. **Příprava webové statické stránky:**
   - Přenesení souborů webové stránky (HTML, CSS, obrázky atd.) do adresáře `/home/web/`.

4. **Konfigurace nového virtualhostu:**
     ```bash
     sudo nano /etc/apache2/sites-available/novy_virtualhost.conf
     ```
     ```
     <VirtualHost *:80>
         ServerAdmin webmaster@example.com
         ServerName novy_virtualhost
         DocumentRoot /home/web

         <Directory /home/web>
             Options Indexes FollowSymLinks
             AllowOverride None
             Require all granted
         </Directory>

         ErrorLog ${APACHE_LOG_DIR}/novy_virtualhost_error.log
         CustomLog ${APACHE_LOG_DIR}/novy_virtualhost_access.log combined
     </VirtualHost>
     ```
     - `ServerAdmin` - e-mail správce serveru.
     - `ServerName` - název nového virtualhostu.
     - `DocumentRoot` - kořenový adresář pro nový virtualhost.
     - `ErrorLog` a `CustomLog` - cesty k log souborům pro tento virtualhost.

5. **Aktivace nového virtualhostu:**
   ```bash
   sudo a2ensite novy_virtualhost.conf
   ```

6. **Restartování služby Apache:**
   ```bash
   sudo systemctl restart apache2
   ```
