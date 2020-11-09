Linux installálás

(segédlet)

CentOS 8.2.2004

# Dokumentum célja

Linux, mint operációs rendszer a Microsoft Windows Server család mellett a másik
jelentős szerv operációs rendszer család. Egyes informatikai szolgáltatások
megvalósításához optimálisabb megoldást ad, mint a Windows. Egy szolgáltatás
bevezetése esetén minden esetben első lépésben meg kell vizsgálni, hogy milyen
operációs rendszer platformon lehet a legjobb megoldást kialakítani.

Ebben a dokumentációban egy step-by-step jelleggel bemutatásra kerül a CentOS
8.2.2004 Linux operációs rendszer installációja. A dokumentum alapját képezi egy
konzultáción bemutatásra kerülő lépésenként átbeszélt telepítésnek, valamint az
ezt követően otthoni munka tárgyát képező egyéni végrehajtásnak. Installáció
virtualizált környezetben történik.

Konfigurációs lépéseket a további Linux dokumentumok tartalmazzák.

# Install média beszerzése

Installálás első lépése, hogy le kell tölteni a médiát. Ehhez el kell dönteni,
hogy melyik Linux disztribúciót kívánjuk telepíteni. Nagyvállalati környezetben
lényeges kérdés a gyártói support, ezért ilyen szempontból a SUSE és a RedHat a
piacvezető (Debian, Ubuntu, … ingyenes, de nem rendelkezik olyan mértékű gyártói
és 3rd party támogatással, ami elvárt). Jelen esetben a RedHat ingyenes
verzióját implementáljuk, ami a CentOS Linux.

Manapság már a telepítő média ISO formátumát használjuk – ami akár kiírható
CR-re, DVD-re, … – mivel a szerverek egyre ritkábban tartalmaznak optikai
meghajtót, valamint ez a formátum támogatott „logikai” optikai meghajtóként való
csatoláshoz.

Első lépésben WEB böngészőben nyissuk meg a következő URL-t:
<https://www.centos.org/download>

A megjelenő oldalon számunkra a CentOS Linux részben az „ISO” oszlopban az
„x86_64” verzióra van szükségünk.

![](media/6f8b78b6f306c469161de09c15b5606d.png)

Ezt választva megjelenik egy lista, ahol kiválaszthatjuk, hogy melyik „mirror”
site-ról szeretnénk letölteni az ISO-t. Innen tetszés szerint választhatunk
egyet:

![](media/1746dc35c0053089500f893cc3aa4ebf.png)

Adott site-on a CentOS 8.2.2004 Linux verzióhoz tartozó médiák listájából
válasszuk ki a CentOS-8.2.2004x86_64-dvd1.iso file-t, és töltsük le, mert ez
tartalmazza az OS-t, valamint több később szükséges tool-t is.

![](media/a2c688b43850abd324a4bcd2d5bfa8bb.png)

# Installáció

Első lépésben a létrehozott virtuális géphez csatoljuk fel a letöltött ISO
állományt:

![](media/7a2863fba3e53df94b8785d1cb3d6919.png)

Kapcsoljuk be a gépet. Ekkor amennyiben a BIOS-ban beállításra került, hogy a
BOOT sorrendben a CD/DVD meghajtó is használható, akkor elindul a telepítés:

![](media/74d4f29b8d43fa2ef0a5dcc5e35e3d01.png)

Itt első lépésben a második pont az alapértelmezett, de ISO állomány esetében
felesleges a „média” tesztelése, ezért válasszuk az első pontot, ami maga az
installáció.

Ezt követően grafikus üzemmódra vált az installer, és első lépésben
kiválaszthatjuk az installáció nyelvét:

![](media/daf3f6e4519ef34f92ac5719573325cf.png)

Érdemes (még ha első lépésben könnyebbnek is tűnik a magyar) az angolt
választani, mivel később bármilyen fellépő probléma esetén a Web-en
nagyságrendekkel több cikk található a megoldáshoz.

Ezt követően megjelenik a „központi” installációs lépernyő:

![](media/bd2ef0c9e825bd66017614405745bd14.png)

Amint az itt felsorolt pontokon végigmentünk, akkor kezdődik valóban az
installáció, azaz itt a konfigurálása történik meg az installer-nek.

Vegyük akkor egyesével a 9 pontot:

1.  **Keyboard**

Angol (English) értéken áll. Nem javasolt átállítani, mert bizonyos esetekben a
konzol emulációjánál egyes karakterek a billentyűzetről nem lesznek elérhetők
(pl.: 0-_\|). Valamint, ezt az elérését a gépnek csak az installáció
időtartamára használjuk (később nagyon speciális esetekben pl.: hibaelhárítás
amikor hálózati réteg nem működik). Tehát ezen most nem változtatunk.

1.  **Language Support**

Angol (English) értéken áll. Nem javasolt átállítani, később igény szerint
módosítható. Tehát ezen most nem változtatunk.

1.  **Time & Date**

Ez a pont segít beállítani az időzónát (ahol a szerver telepítésre kerül) és a
dátumot és pontos időt, valamint lehetőség van az NTP bekapcsolására és
konfigurálására, ami az automatikus időszinkronizálást valósítja meg. Ez utóbbit
nem állítjuk be most, mivel ennek előfeltétele egy hibátlanul működő,
felkonfigurált network réteg.

![](media/e389cbe5777148615cb91b5f923b18ae.png)

A régió legyen Európa (Region: Europe), a város pedig Budapest (City: Budapest).

Amint egy konfigurációs lapon/formon minden szükséges beállítást elvégeztünk,
akkor a bal felső sarokban a „Done” feliratú gomb segítségével térhetünk vissza
a központi installációs oldalra.

1.  **Installation Source**

A felcsatolt ISO file jelen pillanatban az installációs médiánk, ezen nem
változtatunk, itt lehetne egyébként más forrást is megadni.

1.  **Software Selection**

Többek között a CentOS esetében is, vannak gyártói előre elkészített csomagok,
amik egy adott szolgáltatáskörhöz tartozó alkalmazásokat a függőségeikkel együtt
telepítik. Nekünk elég csak ezeket kiválogatni, a többit az installer
összeállítja.

![](media/9b74681dfe7755f0b190f88da0895756.png)

![](media/c66d02b958e44b3785f9e000b63e3433.png)

Jelen esetben cegy „Server” telepítést kérünk (grafikus felület nélkül, azaz a
konzol karakteres), és egy pár hasznos csomagot kérünk hozzá telepíteni:

Hardware Monitoring Utilities  
Performance Tools  
System Tools

Windows esetében is, de Linux installációknál egyértelműen jellemző, hogy csak a
szolgáltatáshoz és a menedzseléshez szükséges alkalmazások kerülnek csak
telepítésre. Ennek az oka: SECURITY (ami nincs felinstallálva, azt egy
rosszindulatú felhasználó/program sem tudja használni).

1.  **Installation Destination**

Jelen esetben még csak egy disk van a szerverhez adva. Amennyiben nem okoz plusz
nehézséget az OS installációs időben ez így kényelmesebb, biztonságosabb,
kevesebb hibázási lehetőséget ad. Amint az operációs rendszer telepítése
befejeződött, a további disk(ek)et is hozzá lehet adni a rendszerhez.
Konfigurációs leírásokban erre kitérünk.

Alapvetően biztonsági okokból egy sokkal tagoltabb felépítést szoktunk használni
Linux operációs rendszerek esetében. Míg Windows-nál a „C:” meghajtóra kerül
„minden”, addig itt a disk-et több partícióra bontjuk funkciók szerint. Továbbá,
míg Windows esetében az egyes partíciók általában betűjellel hivatkozottak (C:,
D:, …), addig UNIX operációs rendszerek esetében mount point-ok vannak, amik az
operációs rendszer egyes könyvtárai lehetnek.

Egy általános felhasználású, operációs rendszer disk felosztása kerül most
bemutatásra az alábbiakban, amit a későbbiekben is érdemes alkalmazni.

Az „Installation Destination” kiválasztását követően a következő lap jelenik
meg:

![](media/a3dac7112b1f3254d116c3125a55340a.png)

Látható, hogy egy darab disk van: sda / 80 GiB.

A „Storage Configuration” szekcióban az „Automatic”-ról állítsuk át „Custom”-ra
a konfigurációs módot. Így manuálisan, mi állíthatjuk be, hogy milyen
partíciókat szeretnénk létrehozni a disk-en. Az itt befektetett plusz munka
később, a rendszer production módban való üzemelésénél hatványozottan
kifizetődik.

„Done” gomb lenyomásával indul a partícionálás, ahol a disk-en nem lesz még
semmilyen partíció, azaz teljesen üres.

![](media/7deb1c9cf9beada3988c2a5501ed7851.png)

Alul a rózsaszín négyzetben látható, a még ki nem osztott terület („Available
space”), míg a szürke négyzetben a teljes terület („Total apce”).

Bal alsó részen a „+” jellel lehet új partíciót létrehozni, a „-” jellel a
kiválasztottat törölni.

Első lépésben a két boot területet hozzuk létre:

/boot/efi létrehozása

Kattintsunk a „+” jelre, a megjelenő ablakban a „Mount Point”-hoz válasszuk a
/boot/efi értéket és a méret legyen 1 GByte, azaz 1024 MiB:

![](media/429ea78f3295608b2332cc2085b5c4ce.png)

Amint ezt beállítottuk, akkor az „Add mount point” gomb segítségével tudjuk a
definíciót jóváhagyni.

Ekkor visszajutunk az előző oldalra. Itt most már azonban látható lesz a
/boot/efi partíció és az adatai:

![](media/b93185f7a162cf9d08bce675840fe895.png)

Ezeken az értékeken ennél a partíciónál ne módosítsunk!

/boot létrehozása

Kattintsunk a „+” jelre, a megjelenő ablakban a „Mount Point”-hoz válasszuk a
/boot értéket és a méret legyen 1 GByte, azaz 1024 MiB:

![](media/c6d49c6e017f9dc600812206544b431a.png)

Amint ezt beállítottuk, akkor az „Add mount point” gomb segítségével tudjuk a
definíciót jóváhagyni.

Ekkor visszajutunk az előző oldalra. Itt most már azonban látható lesz a /boot
partíció is és az adatai:

![](media/51bc0effccb82d2d42793dcb49a8d25a.png)

Ezeken az értékeken ennél a partíciónál ne módosítsunk!

swap létrehozása

SWAP partíció nélkül nem indul el a Linux operációs rendszer. Memória inaktív
lapolási területe. Több is lehet belőle, méretük ekkor összeadódik a
felhasználás során.

Kattintsunk a „+” jelre, a megjelenő ablakban a „Mount Point”-hoz válasszuk a
swap értéket és a méret legyen 4 GByte, azaz 4096 MiB:

![](media/7a52f8c31cab8ff544d3dd20b6c75162.png)

Amint ezt beállítottuk, akkor az „Add mount point” gomb segítségével tudjuk a
definíciót jóváhagyni.

Ekkor visszajutunk az előző oldalra. Itt most már látható lesz a swap partíció
is és az adatai:

![](media/4027f275ff043910bba9174149bd7ce8.png)

Látható, hogy most az installer a „Device Type” esetében már nem a „Standard
Partition”-t használja, hanem az „LVM”-et, ami Logical Volume Manager-t jelenti.
Ez dinamikus bővítését teszi lehetővé a partícióknak, melyek ilyen „Volume
Group”-ra kerülnek.

Módosítsuk a „Volume Group”-ot! Kattintsunk a „Modify” gombra:

![](media/7e296576dab99b70a2bf375478547e86.png)

Adjunk új nevet a volume group-nak, a „Name” mező értékének módosításával:
system_VG

A méretezését pedig a „Size policy”-nél: „As large as possible” értéket, azaz
használja fel az összes rendelkezésre álló helyett.

Ezt követően az alábbiak szerint módosul a partíciós tábla:

![](media/e32090f677fb7eef3a091b3e264a6b50.png)

/var létrehozása

Ide kerül alap esetben több alkalmazás és az operációs rendszer munka és log
adatai. Mérete hiba esetén „elszabadulhat”, ezért korlátozzuk.

Kattintsunk a „+” jelre, a megjelenő ablakban a „Mount Point”-hoz írjuk be a
/var értéket és a méret legyen 8 GByte, azaz 8 GiB:

![](media/030944352fc2f3c07bd574c722fe4b40.png)

Amint ezt beállítottuk, akkor az „Add mount point” gomb segítségével tudjuk a
definíciót jóváhagyni.

Ekkor visszajutunk az előző oldalra. Itt most már azonban látható lesz a /var
partíció is és az adatai:

![](media/1bc20d0a9d4aee194513e13e3cc8d47b.png)

/tmp létrehozása

Ide kerül alap esetben több alkalmazás és az operációs rendszer temporális
állományai. Mérete hiba esetén „elszabadulhat”, ezért korlátozzuk.

Kattintsunk a „+” jelre, a megjelenő ablakban a „Mount Point”-hoz írjuk be a
/tmp értéket és a méret legyen 8 GByte, azaz 8 GiB:

![](media/1a579c2841b88da6253f493d0d6fbb4f.png)

Amint ezt beállítottuk, akkor az „Add mount point” gomb segítségével tudjuk a
definíciót jóváhagyni.

Ekkor visszajutunk az előző oldalra. Itt most már azonban látható lesz a /tmp
partíció is és az adatai:

![](media/f987c707e82afa4f8f8f86ac88d672ec.png)

/ létrehozása

Root („gyökér”) könyvtár. Ez alá kerül minden könyvtár. Az egyes partíciók is az
ez alatti könyvtárak valamelyikére kerülnek mount-olásra.

Kattintsunk a „+” jelre, a megjelenő ablakban a „Mount Point”-hoz írjuk be a /
értéket és a méret ne legyen kitöltve, ezzel jelezzük, hogy minden fennmaradt
területet ide kívánunk felhasználni:

![](media/f273ddcabfcfeaf3ec732a3cc267b665.png)

Amint ezt beállítottuk, akkor az „Add mount point” gomb segítségével tudjuk a
definíciót jóváhagyni.

Ekkor visszajutunk az előző oldalra. Itt most már azonban látható lesz a /tmp
partíció is és az adatai:

![](media/41ceb89dc67654df5ef4c8bab1417a9d.png)

Ezzel elkészültünk az alapvető partícionálással.

Megj.: Amennyiben a szerverre beléphetnek felhasználók, akkor a /home
könyvtárnak is külön partíciót ajánlott létrehozni!

A „Done” gomb megnyomásával hagyhatjuk jóvá és írathatjuk ki az elkészült
partíciós táblát, valamint formattáltathatjuk le a partíciókat az alábbi
jóváhagyást követően („Accept Changes”).

![](media/64b1264a1ef222120807c90aac37bcab.png)

1.  **KDUMP**

A dump-olást nem kívánjuk használni, ezért letiltjuk:

![](media/7d2efdc905951201276a4176845ea0c6.png)

1.  **Network & Host Name**

Ebben a pontban lehet a szerver nevét és hálózati kártyájának/kártyáinak
konfigurálását megadni.

A gép neve legyen: centos82.oktatas.local

IPv4 konfiguráció: 172.31.250.151 / 255.255.255.0 / 172.31.250.1

IPv6 konfiguráció: nem használjuk

![](media/4c461fe920214164862cf2fe5616c109.png)

A „Host Name” mezőbe írjuk be a gép FQDN nevét: centos82.oktatas.local

Ebből a gép neve: centos82

Domain: oktatas.local

![](media/9b558ef5f40cc44f3e4333fa472b3a14.png)

Konfiguráljuk be az IP címet, ehhez a „Configure …” gombot használjuk.

![](media/8b1e0011c42ccc47410bb0ac790d241e.png)

A megjelenő ablakban az „IPv6 Settings” fülön állítsuk át a „Method” értékét
„Ignore”-ra.

Majd az ablakban az „IPv4 Settings” fülön állítsuk át a „Method” értékét
„Manual”-ra.

![](media/cd86c18142d8de7167e97db860ebdeac.png)

„Add” gomb segítségével adjunk hozzá egy IP címet. Ahol az

„Address”: 172.31.250.151

„Netmask”: 255.255.255.0

„Gateway”: 172.31.250.1

„DNS server”: 172.31.252.3

„Search domains”: oktatas.local

„Save” gombbal elmentjük, majd a megjelenő ablakban „ON”-ra billentjük a kártya
állapotát:

![](media/36e589a01e4672e3be0e37e8c5619da8.png)

1.  **Security Policy**

Installáció ezen fázisában nem módosítjuk. Mélyebb konfigurációs ismereteket
követően visszatérünk erre a témakörre.

Ezt követően indul a felkonfigurált paraméterekkel az operációs rendszer
telepítése a „Begin Installation” gomb megnyomásával:

![](media/7372cb279eead71b00951e47e537dcb4.png)

Itt még megadhatjuk a „root” user jelszavát:

![](media/8a17cd513b8f43a43328a9b38e06b8cb.png)

Biztonságos jelszót adjunk meg!

![](media/d556c1ee1251e6364ac14c25286d049c.png)

Installáció végén újra kell indítani a szervert:

![](media/9dca32da585745a31c5ff7659302f99d.png)

Ami boot-olás pillanatában:

![](media/00c49c881e5cbdf8d61c25f4c79c8bc5.png)

Ami az első indulás alkalmával karakteres konzolt biztosít:

![](media/7d21e335fd4e2f517fbf9a9f603fa432.png)

# Oktató anyagok

<https://www.youtube.com/watch?v=I4insAOrsME>

<https://linoxide.com/distros/how-to-install-centos/>

<https://phoenixnap.com/kb/how-to-install-centos-8>
