### 1. Instalace WordPressu:

1. **Aktualizace:**
   ```bash
   sudo apt update
   ```

2. **Instalace Apache, MySQL, PHP:**
   ```bash
   sudo apt install apache2 mysql-server php php-mysql libapache2-mod-php php-cli php-curl php-gd php-mbstring php-xml php-xmlrpc php-soap php-intl php-zip unzip
   ```

3. **Nastavení MySQL:**
     ```bash
     sudo mysql_secure_installation
     ```

4. **Vytvoření databáze pro WordPress:**
     ```bash
     sudo mysql -u root -p
     ```
     ```sql
     CREATE DATABASE wordpress;
     ```
     ```sql
     CREATE USER 'wordpressuser'@'localhost' IDENTIFIED BY 'password';
     GRANT ALL PRIVILEGES ON wordpress.* TO 'wordpressuser'@'localhost';
     FLUSH PRIVILEGES;
     EXIT;
     ```

5. **Stáhnutí a extrakce WordPressu:**
     ```bash
     cd /tmp
     ```
     ```bash
     wget https://wordpress.org/latest.tar.gz
     ```
     ```bash
     tar -xvzf latest.tar.gz
     ```

6. **Přesunutí WordPressu do správného umístění:**
     ```bash
     sudo mv wordpress/* /var/www/html/
     ```

7. **Nastavení oprávnění:**
     ```bash
     sudo chown -R www-data:www-data /var/www/html/
     sudo chmod -R 755 /var/www/html/
     ```

### 2. Konfigurace VirtualHost pro WordPress:

1. **Vytvoření konfiguračního souboru pro VirtualHost:**
     ```bash
     sudo nano /etc/apache2/sites-available/wordpress.conf
     ```
   - Přidejte do souboru následující obsah:
     ```
     <VirtualHost *:80>
         ServerAdmin admin@example.com
         DocumentRoot /var/www/html/
         ServerName your_domain.com
         ServerAlias www.your_domain.com

         <Directory /var/www/html/>
             Options FollowSymLinks
             AllowOverride All
             Require all granted
         </Directory>

         ErrorLog ${APACHE_LOG_DIR}/error.log
         CustomLog ${APACHE_LOG_DIR}/access.log combined
     </VirtualHost>
     ```

2. **Aktivace VirtualHost a restart Apache:**
   ```bash
   sudo a2ensite wordpress.conf
   sudo systemctl restart apache2
   ```

### 3. Dokončení instalace přes webové rozhraní:

**Dokončení instalace pomocí webového rozhraní:**
   - v prohlížeči `http://your_domain.com`
