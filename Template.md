# Windows Server 2016


### Training

| Material                                                                                                    |  Time |
| :---------------------------------------------------------------------------------------------------------- | ----: |
| [Install Windows Server 2016 ](https://www.youtube.com/watch?v=lgOlK9sgY08) | 19:30 |

## Ezeket fogjuk megtanulni

- Windows Server telepítése
- Alapvető funkciók használata
- AD konfiguráció
- DNS konfiguráció
- DHCP konfiguráció
- ResourceMonitor használata
-


### Windows Server 2016 telepítése

Telepítés megkezdése előtt érdemes tanulmányozni

Windows Server 2016
https://docs.microsoft.com/en-us/windows-server/windows-server-2016

System Requirements for Windows 2016 Server
https://docs.microsoft.com/en-us/windows-server/get-started/system-requirements

Important Issues in Windows Server 2016
https://docs.microsoft.com/en-us/windows-server/get-started/windows-server-2016-ga-release-notes


Legjobb gyakorlatok (Best Practicies)

•	Soha ne telepítsünk új rendszert a nyilvános hálózatra.
•	Először indítsuk el a rendszert egy fejlesztői/teszt környezetben, majd utána helyezzük át az éles környezetbe.
•	A patch-eket azonnal installáljuk a telelpítést követően
•	Alkalmazzuk a biztonsági beállításokat a rendszerre.
•	Tűzfal konfigurálása.
•	Telepítsük és frissítsük a víruskereső szoftvert.
•	Ellenőrizzük az összes beállítást.
•	A rendszer frissítések előtt készítsünk teljes biztonsági másolatot!
 
1. Kapcsolja be a rendszert, és helyezze be a telepítőlemezt
a. Ha a BIOS indítási sorrendje nincs beállítva a CD / DVD meghajtóról történő indításra, akkor a telepítés megkezdése előtt módosítani kell ezeket a beállításokat

![](folder/.png)


2. Válasszuk ki a Nyelv, Idő és pénznem formátumot, valamint a Billentyűzet beviteli módot.
3. Kattintsumk a Tovább gombra.
 

 
4. Kattintsunk az Install now-ra	 
a. Ezt az üzenetet fogjátok látni “Setup is starting”.


 	 

b. Az iso telepítés a számítógép javításához is használható.
Ha a fenti Windows telepítő képernyőn a Számítógép javítása lehetőséget választjuk, akkor a rendszer megkéri, hogy végezzük el a számítógép hibakeresését (Troubleshoot) vagy kikapcsolását (Turn off your PC)
	ii. Ha a Hibaelhárítás (Troubleshoot) lehetőséget választjuk, vagy kereshet egy System Image fájlt a Windows helyreállításához, vagy elindíthat egy Parancssorot (Command Prompt).

iii. A témában érdemes átnézni az alábbi dokumentációkat:
https://technet.microsoft.com/library/cc755163.aspx

Wbadmin Start sysrecovery: https://technet.microsoft.com/en-us/library/cc742118(v=ws.11).aspx


### Gyakorló feladatok, melyeket önállóan kell megoldani.

- Telepítsünk egy Virtualboxot
-Tölstük le a Windows Server 2016 valamelyik verzióját és telepítsük