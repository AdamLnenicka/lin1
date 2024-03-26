Pro splnění úkolu 5 na serveru Debian-02, který bude sloužit jako zálohovací server, následujte tyto kroky:

1. **Instalace SSH serveru:**
   - Otevřete terminál na serveru Debian-02.
   - Aktualizujte seznam dostupných balíčků:
     ```
     sudo apt update
     ```
   - Nainstalujte SSH server:
     ```
     sudo apt install openssh-server
     ```

2. **Konfigurace SSH serveru pro přihlášení bez hesla:**
   - Otevřete konfigurační soubor SSH serveru pro úpravy:
     ```
     sudo nano /etc/ssh/sshd_config
     ```
   - Ujistěte se, že přihlašování pomocí hesla je povoleno (výchozí nastavení):
     ```
     PasswordAuthentication yes
     ```
   - Ujistěte se, že přihlašování pomocí SSH klíčů je povoleno:
     ```
     PubkeyAuthentication yes
     ```
   - Uložte provedené změny a zavřete editor.
   - Restartujte SSH server, aby se změny projevily:
     ```
     sudo systemctl restart ssh
     ```

3. **Vytvoření adresáře pro zálohy:**
   - Vytvořte adresář `/share`, který bude sloužit pro zálohy:
     ```
     sudo mkdir /share
     ```

4. **Nastavení oprávnění adresáře /share:**
     ```
     sudo chown -R student:student /share
     ```
     ```
     sudo chmod -R 700 /share
     ```

5. **Konfigurace přihlašování bez hesla pro uživatele student:**
   - eřejný klíč do souboru `~/.ssh/authorized_keys` ve složce domovského adresáře `student` na serveru Debian-02.

6. **Vytvoření podadresářů s hostnames:**
   - V adresáři `/share` podadresáře s hostnames druhého serveru a klienta.
