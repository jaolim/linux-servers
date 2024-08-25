# h1 Oma Linux

## x) Tiivistelmät

## Hyvän raportin kirjoittaminen
Raportointiohjeet ovat tiivistetty Tero Karvisen 2006 ohjeista.

Hyvän raportin tulisi olla täsmällinen, selkeä ja toistettava. Tämä siis tarkoittaa, että sekä ympäristön, että siinä suoritettavien toimenpiteiden tulee ilmetä raportista. Käytetyt lähteet tulee merkitä raporttiin.

Esitysasun tulee olla selkeä käyttäen väliotsikoita ja kuvia (tekijänoikeudet huomioiden) kun on sopivaa.

Vakavia virheitä raportissa raportissa ovat sepittäminen, plagiointi, ja tekijänoikeuksien loukkaus.

## Free Software Foundation - Vapaa Ohjelma
Tiivistelmä on kirjoitettu FSF:n What is Free Software? Artikkelin perusteella.

### Vapaan ohjelman määritys

Free Software Foundation määrittää vapaan ohjelman ohjelmaksi, jota voi ajaa, muokata, tutkia, kopioida, ja julkaista haluamallaan tavalla.
Edellytys tälle on pääsy lähtekoodiin.

### Vapaan ohjelman kaupallisuus

Oikeus käyttää ohjelmaa kaupallisesti on turvattava tai se ei ole vapaa ohjelma.
Tämän on looginen tulkinta vapaudesta, mutta voi aiheuttaa hämmennystä jos vapaan (eng. free) tulkitsee ilmaiseksi.

Tulkinnan taustalla on myös tavoita levittää vapaata ohjelmaa ja lopulta saada se korvaamaan ei-vapaat vaihtoehdot. Tämän toteutuminen on mahdotonta, jos vapaata ohjelmaa ei saa käyttää kaupallisesti.

### Vapaalle ohjelmalle hyväksyttävät jakelusäännöt
On olemassa joitain ohjelman jakeluun liittyviä sääntöjä, esimerkiksi Copyleft, joiden FSF katsoo olevan hyväksyttäviä vapaassa ohjelmassa.
Pelkistetysti Copyleft tarkoittaa, että uudelleenjaettessa ohjelmaa sen keskeisiä vapauksia ei saa rajoittaa.

Myös säännöt ohjelman uudelleenjakelusta, kuten kielto julkaista muokattua versiota samalla nimellä, ovat hyväksyttäviä, jos ne eivät oleellisesti rajoita vapautta julkaista tai rakentaa muokattuja versioita.

### Vapaan ohjelman määritelmä käytännössä
Kriteerien tulkitseminen vapaalle ohjelmalle edellyttää tarkkaa harkintaa ja  FSF katsoo, että ohjelman on noudatettava vapaan ohjelman periaatteita myös hengessä tarkoin määriteltyjen sääntöjen lisäksi.

### Vapaan softan tuolla puolen
FSF:n mukaan myös vapaan ohjelmiston manuaalien on oltava vapaita, koska ne ovat de facto osa ohjelmistoa.
Vapaan ohjelman määritelmän voi myös jatkaa samoilla periaatteilla kattamaan ohjelmien ulkopuolisia asioita.

## a) Asenna Linux virtuaalikoneeseen
Tähtävä suoritettiin Tero Karvasin 2023 asennusohjeita noudattaen. Prosessissa meni kokonaisuudessaan 1h 10min ja ainoa vastaan tullut ongelma oli puuttuva riippuvuus VirtualBoxin hallinnointiin Python scripteillä (todennäköisesti turha ominaisuus, mutta asensimpa kuitenkin), jonka selvittäminen tapahtui muutamassa minuutissa.

Ympäristö: 
- Käyttöjärjestelmä: Windows 11 Education 23H2
- Prosessori: AMD Ryzen 3900XT 12-core
- RAM: 32GB
- Näytönohjain: Nvidia Geforce 3080 RTX
- Kiintolevy: Samsung 2 TB M.2 SSD

Latasin VirtualBox 7.0.20 exen ja Debian live 12.6.0 imagen koneelle.
Lähdin asentamaan VirtualBoxia kaikilla ominaisuuksilla. Keskeytin ensimmäisen asennuksen asentaakseni puuttuvat riippuvuudet Python tukeen.

![VirtualBox Install](1_virtualbox_install.png)

![Python Install](2_python_install.png)

Asensin puuttuvat riippuvuudet ja asensin VirtualBoxin kaikilla ominaisuuksilla.

Tein uuden virtuaalikoneen VirtualBoxiin seuraavilla asetuksilla:

![Virtual Machine](3_virtual_machine.png)

Boottasin Debianin live version ja varmistin hiiren, näppäimistön ja internet yhteyden toimivuuden, sekä ajoin yksinkertaisen komennon shellissä.

![Shell](5_hello_debian.png)

Asensin Debianin seuraavilla asetuksilla:

![Settings](6_install_settings.png)

Boottasin virtuaalikoneen ja varmistin koneen speksien olevan oikein.

![Debian Running](8_debian_running.png)

## x)Vapaaehtoinen bonus: suosikkiohjelmani Linuxilla. Tee ja raportoi jokin yksinkertainen toimenpide haluamallasi Linux-ohjelmalla.

Hain Googlesta tietoa Linux CPU testeistä ja päädyin Sysbench ohjelmaan.

Sysbench install:

![Sysbench Install](h1_x1_sysbench_install.png)

Sysbench manuaali (man sysbench komento):

![Sysbench Manual](h1_x2_sysbench_manual.png)

Testin asetukset (neljän ytimen testi):

![Benchmark Parameters](h1_x3_benchmark_parameters.png)

Testitulokset:

![Benchmark Results](h1_x4_benchmark_results.png)

Yhteenvetona voin todeta, etten osannut tulkita testituloksia, mutta koska virtuaalikone tai sitä pyörittävä pöytäkone eivät kaatuneet, pidin sitä onnistuneena.


## Lähteet
Karvinen, Tero 2024: Tehtävä h1 Oma Linux. https://terokarvinen.com/linux-palvelimet/#h1-oma-linux

Karvinen, Tero 2006: Raportin kirjoittaminen. https://terokarvinen.com/2006/raportin-kirjoittaminen-4/

FSF: What is Free Software: https://www.gnu.org/philosophy/free-sw.html

Karvinen, Tero 2023: Virtual linux asennusohjeet: https://terokarvinen.com/2021/install-debian-on-virtualbox/

Debian image: https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/debian-live-12.6.0-amd64-xfce.iso

VirtualBox lataussivu: https://www.virtualbox.org/wiki/Downloads

Sysbench benchmark ohjelma: https://github.com/akopytov/sysbench
