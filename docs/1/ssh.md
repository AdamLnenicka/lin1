

1. **Kontrola zda SSH není přítomné:**

   ```
   sudo apt update
   sudo apt install openssh-server
   sudo systemctl status ssh
   ```

   Pokud není spuštěná:

   ```
   sudo systemctl start ssh
   ```

2. **Nastavení firewallu:**
   Pokud je aktivovaný firewall (například iptables nebo ufw):

   ```
   sudo ufw allow ssh
   ```

3. **přihlašování pomocí hesla nebo klíčů:**
   - přihlašování pomocí hesla soubor `/etc/ssh/sshd_config`, řádek s `PasswordAuthentication`:

     ```
     PasswordAuthentication yes
     ```

   - pomocí SSH klíčů v souboru `/etc/ssh/sshd_config` řádek s `PubkeyAuthentication` nastaven na `yes`:

     ```
     PubkeyAuthentication yes
     ```

4. **Restartovat SSH službu:**
   ```
   sudo systemctl restart ssh
   ```

Pro získání SSH klíče:

1. **Vygenerování SSH klíče:**
   - Spustit příkaz `ssh-keygen`. Typicky `~/.ssh/id_rsa` pro privátní klíč a `~/.ssh/id_rsa.pub` pro veřejný klíč.

2. **Kopírování veřejného klíče na server:**
   - zkopírovat obsah vašeho veřejného klíče `~/.ssh/id_rsa.pub` na server
   - použít příkaz `ssh-copy-id`
     ```
     ssh-copy-id username@server_ip
     ```

3. **Přihlášení na server bez hesla:**
  - spustit příkaz `ssh username@server_ip`
