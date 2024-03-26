
 **Vytvoření nového bash skriptu:**
   - Spusťte příkaz:
     ```
     nano test_packages.sh
     ```
     
     ```bash
     #!/bin/bash
     
     # Funkce pro testování instalace balíčku
     test_package() {
         if dpkg -s $1 &> /dev/null; then
             echo "Package $1 is installed"
         else
             echo "Package $1 is not installed"
         fi
     }
     
     # Testování balíčků
     test_package "tar"
     test_package "telnet"
     test_package "htop"
     ```

**Udělení oprávnění pro spuštění:**
     ```
     chmod +x test_packages.sh
     ```
**Přesunutí skriptu do domovského adresáře uživatele student:**
     ```
     mv test_packages.sh /home/student/
     ```
 **Testování skriptu:**
   - Spusťte skript pomocí:
     ```
     ./test_packages.sh
     ```

Skript by měl zkontrolovat instalaci balíčků `tar`, `telnet` a `htop` a vypsat zprávy o tom, zda jsou nainstalovány či nikoliv.
