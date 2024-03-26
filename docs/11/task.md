
### Instalace a konfigurace Ansible na klientovi Ubuntu-01:

1. **Instalace Ansible:**
   ```bash
   sudo apt update
   sudo apt install ansible
   ```

2. **Vytvoření inventáře:**
     ```bash
     nano ~/inventory.ini
     ```
     ```
     [servers]
     debian-01
     debian-02
     ```

3. **Konfigurace Ansible:**
     ```bash
     sudo nano /etc/ansible/ansible.cfg
     ```
   - Odkomentuj
     ```
     inventory      = ~/inventory.ini
     ```

### Vytvoření bash skriptu pro otestování konektivity:

1. **Vytvoření bash skriptu:**
     ```bash
     nano ~/ping.sh
     ```
     ```bash
     #!/bin/bash
     
     # Otestování konektivity ke všem serverům pomocí Ansible ping modulu
     ansible servers -m ping
     ```

2. **Nastavení oprávnění:**
     ```bash
     chmod +x ~/ping.sh
     ```

3. **Spouštění skriptu:**
     ```bash
     ~/ping.sh
     ```
