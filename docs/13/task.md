
**Pro Ubuntu klienta (ubuntu-01):**
1. V terminálu spustit příkaz pro změnu hostname:
   ```
   sudo hostnamectl set-hostname ubuntu-01
   ```
2. Potvrdit změnu zadáním hesla správce (sudo).
3. Kontrola, zda byl hostname úspěšně změněn:
   ```
   hostname
   ```
   Měl by vypsat `ubuntu-01`.

**Pro Debian servery (debian-01, debian-02):**
1. Připojení se k Debian serverům přes SSH nebo terminál přímo na serverech.
2. Spusťte příkaz pro změnu hostname:
   ```
   sudo hostnamectl set-hostname debian-01
   ```
   nebo
   ```
   sudo hostnamectl set-hostname debian-02
   ```
3. Zadání hesla správce (sudo).
4. Kontrola, zda byl hostname úspěšně změněn:
   ```
   hostname
   ```
   Měl by vypsat `debian-01` nebo `debian-02`.

Tímto způsobem by měly být nastaveny hostnames na Ubuntu klientovi a Debian serverech podle zadaných specifikací.