
**Pro Ubuntu klienta (ubuntu-01):**
1. pro změnu hostname:
   ```
   sudo hostnamectl set-hostname ubuntu-01
   ```
2. Potvrdit změnu zadáním hesla správce (sudo).
3. Kontrola:
   ```
   hostname
   ```

**Pro Debian servery (debian-01, debian-02):**
1. Připojení se k Debian serverům přes SSH nebo terminál přímo na serverech.
2. pro změnu hostname:
   ```
   sudo hostnamectl set-hostname debian-01
   ```
   nebo
   ```
   sudo hostnamectl set-hostname debian-02
   ```
3. Zadání hesla správce (sudo).
4. Kontrola:
   ```
   hostname
   ```
